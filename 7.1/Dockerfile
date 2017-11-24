FROM mileschou/php-xdebug:7.1

# Install extensions
RUN set -xe && \
        apk add --no-cache \
            libxml2-dev \
        && \
        docker-php-ext-install \
            pdo_mysql \
            soap
