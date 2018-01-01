FROM djschaper/shellcheck:0.4.7 as builder
# Copy binary from already built image. This is a modified multi-stage build
# with the build stage already finalized instead of building during the
# first stage.

FROM alpine:3.7 as runner

COPY --from=builder /bin/shellcheck /bin/

CMD ["/bin/shellcheck"]
