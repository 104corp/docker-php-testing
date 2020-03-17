FROM mileschou/xdebug:7.3-apache

ENV COMPOSER_PATH /usr/local/bin/composer

# Install extensions
RUN set -xe && \
        apt-get update -y && apt-get install -y --no-install-recommends --no-install-suggests \
            libgmp-dev \
            libjpeg-dev \
            libmemcached-dev \
            libpng-dev \
            libxml2-dev \
            libzip-dev \
            zlib1g-dev \
        && \
        apt-get clean && rm -rf /var/lib/apt/lists/* \
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
        php -m

# Install Composer and configure
COPY --from=composer:1.9.1 /usr/bin/composer /usr/local/bin/composer

RUN set -xe && \
        composer global require hirak/prestissimo && \
        composer clear-cache
