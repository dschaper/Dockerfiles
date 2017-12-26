FROM djschaper/minideb-git:stretch as builder

# Set environment for building binary
ENV HOME=/opt/shellcheck

# Install GHC and cabal
RUN install_packages \
      cabal-install \
      ghc

WORKDIR /opt/shellcheck

# Copy the shell check code to be built https://github.com/koalaman/shellcheck
RUN git clone --depth=1 -b master https://github.com/koalaman/shellcheck .

RUN cabal update && \
    cabal install --dependencies-only && \
    cabal build Paths_ShellCheck && \
    ghc -optl-static -optl-pthread -idist/build/autogen --make shellcheck

FROM alpine:3.7 as runner

COPY --from=builder /opt/shellcheck/shellcheck /bin/

CMD ["/bin/shellcheck"]
