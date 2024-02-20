# Créer un Dockerfile pour cette application en mode production
FROM debian as latest

# Installation rust nightly
RUN apt-get update && apt-get install -y curl build-essential libpq-dev 
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y --default-toolchain nightly
ENV PATH="/root/.cargo/bin:${PATH}"

WORKDIR /blog
COPY . .


RUN cargo install diesel_cli --no-default-features --features postgres

EXPOSE 8000


# Build l'app rust
RUN cargo build

# migration de la bd et  lancement de lab
CMD diesel migration run && cargo run
