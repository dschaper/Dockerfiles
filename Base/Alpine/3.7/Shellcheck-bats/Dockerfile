FROM djschaper/shellcheck-alpine3.7:0.4.7

RUN apk --no-cache --virtual .run-depends add \
    bash

WORKDIR /srv/bats/

ADD bats-core/ .

RUN ./install.sh /usr/local

CMD ["/bin/sh"]
