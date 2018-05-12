FROM mileschou/php-xdebug:5.6

ENV COMPOSER_PATH /usr/local/bin/composer

# Install extensions
RUN set -xe && \
        apk add --no-cache --virtual .build-deps \
            libjpeg-turbo-dev \
            libmcrypt-dev \
            libpng-dev \
            libxml2-dev \
            zlib-dev \
        && \
        docker-php-ext-configure gd \
            --with-jpeg-dir=/usr/include/ \
            --with-png-dir=/usr/include/ \
        && \
        docker-php-ext-install \
            exif \
            gd \
            mcrypt \
            pdo_mysql \
            soap \
            zip \
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
