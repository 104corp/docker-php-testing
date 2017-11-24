FROM mileschou/php-xdebug:5.5

# Install extensions
RUN set -xe && \
        apk add --no-cache --virtual .build-deps \
            libjpeg-turbo-dev \
            libpng-dev \
            libxml2-dev \
        && \
        docker-php-ext-configure gd \
            --with-jpeg-dir=/usr/include/ \
            --with-png-dir=/usr/include/ \
        && \
        docker-php-ext-install \
            exif \
            gd \
            pdo_mysql \
            soap
