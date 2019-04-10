FROM mileschou/php-xdebug:5.5-apache

ENV COMPOSER_PATH /usr/local/bin/composer

# Install extensions
RUN set -xe && \
        # workaround for archive source list
        # See https://unix.stackexchange.com/questions/508724/failed-to-fetch-jessie-backports-repository/508791
        sed -i '/deb http:\/\/httpredir.debian.org\/debian jessie-updates main/d' /etc/apt/sources.list \
        && \
        apt-get update -y && apt-get install -y --no-install-recommends --no-install-suggests \
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
        docker-php-ext-install -j $(getconf _NPROCESSORS_ONLN) \
            exif \
            gd \
            mcrypt \
            pdo_mysql \
            soap \
            zip \
        && \
        pecl install \
            memcached-2.2.0 \
            redis \
        && \
        docker-php-ext-enable \
            memcached \
            redis \
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
