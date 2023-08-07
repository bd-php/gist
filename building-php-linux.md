# Build PHP From Source [Linux]
```
#!/bin/bash
sudo apt update && \
sudo apt dist-upgrade && \
sudo apt install \
 build-essential \
 autoconf \
 libtool \
 bison \
 re2c \
 pkg-config \
 libsqlite3-dev \
 libpq-dev \
 libonig-dev \
 libfcgi-dev \
 libfcgi0ldbl \
 libjpeg-dev \
 libpng-dev \
 libssl-dev \
 libxml2-dev \
 libcurl4-openssl-dev \
 libxpm-dev \
 libgd-dev \
 libmysqlclient-dev \
 libfreetype6-dev \
 libxslt1-dev \
 libpspell-dev \
 libzip-dev \
 libgccjit-10-dev && \
git clone https://github.com/php/php-src.git --depth=1 && \
cd php-src && \
./buildconf && \
sudo ./configure \
 --prefix=/opt/php/php8 \
 --enable-cli \
 --enable-fpm \
 --enable-intl \
 --enable-mbstring \
 --enable-opcache \
 --enable-sockets \
 --enable-soap \
 --with-curl \
 --with-freetype \
 --with-fpm-user=www-data \
 --with-fpm-group=www-data \
 --with-jpeg \
 --with-mysql-sock \
 --with-mysqli \
 --with-openssl \
 --with-pdo-mysql \
 --with-pgsql \
 --with-xsl \
 --with-zlib && \
make -j4 && \
./sapi/cli/php -v
```

# Notes
# View all options
```
./configure --help
```
# Install
```
sudo make install
```
