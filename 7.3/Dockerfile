FROM mileschou/xdebug:7.3

ENV COMPOSER_PATH /usr/local/bin/composer

# Install extensions
RUN set -xe && \
        # Runtime dependency
        apk add --no-cache \
            libgmpxx \
            libjpeg-turbo \
            libmemcached-libs \
            libpng \
            libzip \
        && \
        apk add --no-cache --virtual .build-deps \
            autoconf \
            cyrus-sasl-dev \
            g++ \
            gmp-dev \
            libjpeg-turbo-dev \
            libmemcached-dev \
            libpng-dev \
            libxml2-dev \
            libzip-dev \
            make \
            zlib-dev \
        && \
        docker-php-ext-configure gd \
            --with-jpeg-dir=/usr/include/ \
            --with-png-dir=/usr/include/ \
        && \
        docker-php-ext-install -j $(getconf _NPROCESSORS_ONLN) \
            exif \
            gd \
            gmp \
            pdo_mysql \
            soap \
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
RUN set -xe && \
        curl -sS https://getcomposer.org/installer | php && \
        chmod +x composer.phar && \
        mv composer.phar ${COMPOSER_PATH} && \
        composer --version && \
        composer global require hirak/prestissimo && \
        composer clear-cache
