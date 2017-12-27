FROM djschaper/shellcheck-alpine3.7:0.4.7

RUN apk --no-cache --virtual .run-depends add \
    bash

RUN git clone https://github.com/bats-core/bats-core.git /opt/bats/ && \
    /opt/bats/install.sh /usr/local

CMD ["/bin/sh"]
