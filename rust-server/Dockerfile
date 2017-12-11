FROM ekidd/rust-musl-builder

ADD . ./
RUN sudo chown -R rust:rust /home/rust

RUN cargo build --release

EXPOSE 8000
CMD ["/home/rust/src/target/x86_64-unknown-linux-musl/release/rust-server"]