FROM php:7.2

MAINTAINER Greene Liu <greene@jetfuel.com.tw>

RUN apt-get update && apt-get install -y --no-install-recommends \
    gnupg \
    zlib1g-dev \
    libpq-dev \
    libpng-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libxpm-dev \
    libwebp-dev

RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -

RUN apt-get install -y --no-install-recommends \
    openssh-client \
    git \
    nodejs \
 && apt-get clean \
 && rm -r /var/lib/apt/lists/*

RUN docker-php-ext-install -j$(nproc) zip pdo_mysql pdo_pgsql \
 && docker-php-ext-configure gd \
    --with-freetype-dir=/usr/include/ \
    --with-jpeg-dir=/usr/include/ \
    --with-xpm-dir=/usr/include \
    --with-webp-dir=/usr/include/ \
 && docker-php-ext-install -j$(nproc) gd

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
