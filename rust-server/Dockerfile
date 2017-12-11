FROM ekidd/rust-musl-builder

ADD . ./
RUN sudo chown -R rust:rust /home/rust

RUN cargo build --release

EXPOSE 3000
CMD ["target/release/rust-from-scratch"]