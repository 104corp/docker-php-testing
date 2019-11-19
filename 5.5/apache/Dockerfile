FROM mileschou/xdebug:5.5-apache

ENV COMPOSER_PATH /usr/local/bin/composer

# Install extensions
RUN set -xe && \
        # workaround for archive source list
        # See https://unix.stackexchange.com/questions/508724/failed-to-fetch-jessie-backports-repository/508791
        sed -i '/deb http:\/\/httpredir.debian.org\/debian jessie-updates main/d' /etc/apt/sources.list \
        && \
        apt-get update -y && apt-get install -y --no-install-recommends --no-install-suggests \
            libgmp-dev \
            libjpeg-dev \
            libmcrypt-dev \
            libmemcached-dev \
            libpng-dev \
            libxml2-dev \
            zlib1g-dev \
        && \
        apt-get clean && rm -rf /var/lib/apt/lists/* \
        && \
        docker-php-ext-configure gd \
            --with-jpeg-dir=/usr/include/ \
            --with-png-dir=/usr/include/ \
        && \
        # See https://stackoverflow.com/questions/19894168
        ln -s /usr/include/x86_64-linux-gnu/gmp.h /usr/include/gmp.h \
        && \
        docker-php-ext-install -j $(getconf _NPROCESSORS_ONLN) \
            exif \
            gd \
            gmp \
            mcrypt \
            pdo_mysql \
            soap \
            zip \
        && \
        pecl install \
            memcached-2.2.0 \
            redis-4.3.0 \
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
