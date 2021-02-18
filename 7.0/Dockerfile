FROM ghcr.io/mileschou/xdebug:7.0

ENV COMPOSER_PATH /usr/local/bin/composer

# Install extensions
RUN set -xe && \
        # Runtime dependency
        apk add --no-cache \
            libgmpxx \
            libjpeg-turbo \
            libmcrypt \
            libmemcached-libs \
            libpng \
            make \
        && \
        apk add --no-cache --virtual .build-deps \
            autoconf \
            cyrus-sasl-dev \
            g++ \
            gmp-dev \
            libjpeg-turbo-dev \
            libmcrypt-dev \
            libmemcached-dev \
            libpng-dev \
            libxml2-dev \
            zlib-dev \
        && \
        docker-php-ext-configure gd \
            --with-jpeg-dir=/usr/include/ \
            --with-png-dir=/usr/include/ \
        && \
        docker-php-ext-install -j $(getconf _NPROCESSORS_ONLN) \
            bcmath \
            exif \
            gd \
            gmp \
            mcrypt \
            pdo_mysql \
            soap \
            sockets \
            zip \
        && \
        pecl install \
            memcached \
            redis \
        && \
        docker-php-ext-enable \
            memcached \
            redis \
        && \
        apk del .build-deps \
        && \
        php -m

# Install Composer and configure
COPY --from=composer:1 /usr/bin/composer /usr/local/bin/composer

RUN set -xe && \
        composer global require hirak/prestissimo && \
        composer clear-cache
