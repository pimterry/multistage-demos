FROM ekidd/rust-musl-builder as build
ADD . ./
RUN sudo chown -R rust:rust /home/rust
RUN cargo build --release

FROM scratch
COPY --from=build /home/rust/src/target/x86_64-unknown-linux-musl/release/rust-server /
EXPOSE 8000
CMD ["/rust-server"]