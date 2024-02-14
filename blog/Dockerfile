# Créer un Dockerfile pour cette application en mode production
FROM debian as latest

#(jsp si nightly )
FROM rust as latest


WORKDIR /blog
COPY . .
ENV DATABASE_URL=postgres://thomas:admin@db:5432/blog
ENV ROCKET_ADDRESS=0.0.0.0

RUN cargo install diesel_cli --no-default-features --features postgres

EXPOSE 8000


# Build the Rust app (pas sur)
RUN cargo build

# Set the command to run the Rust app (pas sur)
CMD cargo run