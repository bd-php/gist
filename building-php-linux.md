### Build PHP From Source [Linux]
```
#!/bin/bash
sudo apt update && \
sudo apt dist-upgrade && \
sudo apt install build-essential autoconf libtool bison re2c pkg-config libxml2-dev libssl-dev && \
git clone https://github.com/php/php-src.git --depth=1 && \
cd php-src && \
./buildconf && \
./configure --with-readline --enable-ftp --with-openssl --disable-phar && \
make -j4 && \
./sapi/cli/php -v
```
