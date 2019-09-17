FROM php:7.1-fpm

RUN apt-get update && apt-get install -y libmcrypt-dev && \
     docker-php-ext-install mcrypt
RUN apt-get -y install libxml2-dev && \
    docker-php-ext-install soap
RUN apt-get -y install libxslt-dev && \
    docker-php-ext-install xsl
RUN docker-php-ext-install bcmath
RUN apt-get install -y zlib1g-dev libicu-dev g++ && \
    docker-php-ext-configure intl && \
    docker-php-ext-install intl
RUN apt-get install -yqq && \
      docker-php-ext-install zip
RUN docker-php-ext-install pdo_mysql
RUN apt-get install -y libgmp-dev && \
    docker-php-ext-install gmp
RUN apt-get install -y jpegoptim optipng pngquant gifsicle
RUN apt-get install -y libmagickwand-dev imagemagick && \
    pecl install imagick && \
    docker-php-ext-enable imagick
# RUN apt-get install libz-dev libpng-dev libjpeg-dev libfreetype6-dev libxpm-dev libx11-dev libxt-dev libfontconfig-dev libvpx-dev libtiff-dev -y && \
#     docker-php-ext-install gd
# RUN docker-php-ext-configure gd \
#         --with-freetype-dir=/usr/lib/ \
#         --with-png-dir=/usr/lib/ \
#         --with-jpeg-dir=/usr/lib/ \
#         --with-gd
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd