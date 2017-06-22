FROM php:5.6

MAINTAINER Greene Liu <greene@jetfuel.com.tw>

RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -

RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    nodejs \
    libcurl4-gnutls-dev \
    libicu-dev \
    libmcrypt-dev \
    libvpx-dev \
    libjpeg-dev \
    libpng-dev \
    libxpm-dev \
    zlib1g-dev \
    libfreetype6-dev \
    libxml2-dev \
    libexpat1-dev \
    libbz2-dev \
    libgmp3-dev \
    libldap2-dev \
    unixodbc-dev \
    libpq-dev \
    libsqlite3-dev \
    libaspell-dev \
    libsnmp-dev \
    libpcre3-dev \
    libtidy-dev \
 && apt-get clean \
 && rm -r /var/lib/apt/lists/*

RUN docker-php-ext-install \
    mbstring \
    mcrypt \
    pdo_mysql \
    curl \
    json \
    intl \
    gd \
    xml \
    zip \
    bz2 \
    opcache

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
