FROM rustlang/rust:nightly-slim

RUN apt-get update && apt-get install -y build-essential libpq-dev 

WORKDIR /blog
COPY . .

RUN cargo install diesel_cli --no-default-features --features postgres

EXPOSE 8000

CMD diesel migration run && cargo run

