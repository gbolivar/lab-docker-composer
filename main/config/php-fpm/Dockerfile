FROM phpdockerio/php73-fpm:latest
WORKDIR /apps

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

# update pack and install commun pack
RUN apt-get update -y
RUN apt-get install -y \
    vim \
    zip \
    unzip \
    git \
    git-core \
    curl \
    libcurl4 \
    libcurl4-openssl-dev \
    redis-tools \
    cron

# Install selected extensions and other stuff
RUN apt-get install -y \
    php7.3-memcached \
    php7.3-mysql \
    php7.3-pgsql \
    php7.3-redis \
    php7.3-sqlite3 \
    php7.3-xdebug \
    php7.3-gd \
    php7.3-intl \
    php7.3-mongodb \
    php7.3-soap \
    php7.3-zip \
    php7.3-curl \
    php7.3-xsl \
    php7.3-dev

RUN apt-get upgrade -y

# Composer
RUN curl https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer

# Clean
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /var/tmp/* /usr/share/doc/