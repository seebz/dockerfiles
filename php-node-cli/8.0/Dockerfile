
# Dependencies
FROM node:current-alpine AS node
FROM composer:latest AS composer

# Main
FROM php:8.0-cli-alpine


# composer dependencies
RUN set -eux ; \
  apk add --no-cache --virtual .composer-rundeps \
    p7zip \
    bash \
    coreutils \
    git \
    make \
    openssh-client \
    patch \
    subversion \
    tini \
    unzip \
    zip \
    $([ "$(apk --print-arch)" != "x86" ] && echo mercurial)

RUN printf "# composer php cli ini settings\n\
date.timezone=UTC\n\
memory_limit=-1\n\
" > $PHP_INI_DIR/php-cli.ini

# composer executable
COPY --from=composer /usr/bin/composer /usr/local/bin/composer


# node_modules
COPY --from=node /usr/local/lib/node_modules /usr/local/lib/node_modules

# node executable
COPY --from=node /usr/local/bin/node /usr/local/bin/node

# npm executable (symlink)
RUN ln -s ../lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npm

# npx executable (symlink)
RUN ln -s ../lib/node_modules/npm/bin/npx-cli.js /usr/local/bin/npx


# smoke tests
RUN php --version \
  && composer --version \
  && node --version \
  && npm --version \
  && npx --version


ENTRYPOINT [""]
