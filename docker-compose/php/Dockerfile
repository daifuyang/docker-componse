FROM php:7.1-fpm

RUN echo "deb https://mirrors.aliyun.com/debian/ buster main non-free contrib" > /etc/apt/sources.list \
echo "deb-src https://mirrors.aliyun.com/debian/ buster main non-free contrib" >> /etc/apt/sources.list \
echo "deb https://mirrors.aliyun.com/debian-security buster/updates main" >> /etc/apt/sources.list \
echo "deb-src https://mirrors.aliyun.com/debian-security buster/updates main" >> /etc/apt/sources.list \
echo "deb https://mirrors.aliyun.com/debian/ buster-updates main non-free contrib" >> /etc/apt/sources.list \
echo "deb-src https://mirrors.aliyun.com/debian/ buster-updates main non-free contrib" >> /etc/apt/sources.list \
echo "deb https://mirrors.aliyun.com/debian/ buster-backports main non-free contrib" >> /etc/apt/sources.list \
echo "deb-src https://mirrors.aliyun.com/debian/ buster-backports main non-free contrib" >> /etc/apt/sources.list


RUN  apt-get update && apt-get install -y \ 
    libfreetype6-dev \ 
    libjpeg62-turbo-dev \ 
    libmcrypt-dev \ 
    libpng-dev \ 
    && docker-php-ext-install -j $(nproc) iconv mcrypt \ 
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \ 
    && docker-php-ext-install -j $(nproc) gd \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install zip