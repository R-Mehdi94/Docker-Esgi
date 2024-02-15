# Créer un Dockerfile pour cette application en mode production
FROM debian as latest

#(nightly normalement mais marche pas )
RUN apt-get update && apt-get install -y curl build-essential libpq-dev 
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh 

WORKDIR /blog
COPY . .


RUN cargo install diesel_cli --no-default-features --features postgres

EXPOSE 8000


# Build the Rust app (pas sur)
RUN cargo build
# Set the command to run the Rust app (pas sur)
CMD cargo run