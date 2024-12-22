FROM bitnami/php-fpm

# install dev tools
RUN apt-get update -y && apt-get install -y \
    autoconf \
    build-essential \
    wget \
    git

#RUN pecl install redis && docker-php-ext-enable redis

# install redis extension
RUN cd /root \
    && wget https://pecl.php.net/get/redis-6.1.0.tgz \
    && tar xzf redis-6.1.0.tgz && cd redis-6.1.0 \
    && phpize \
    && ./configure \
    && make \
    && make install
RUN echo "extension=redis.so" >> /opt/bitnami/php/etc/php.ini
