FROM wordpress:php8.2-apache

# 基本ツール（任意だがデバッグに便利）
RUN apt-get update \
  && apt-get install -y --no-install-recommends \
     git unzip less vim \
  && rm -rf /var/lib/apt/lists/*

# Xdebug
RUN pecl install xdebug \
  && docker-php-ext-enable xdebug

# php.ini / xdebug.ini
COPY php.ini /usr/local/etc/php/php.ini
COPY conf.d/xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

# Apache rewrite（パーマリンク用）
RUN a2enmod rewrite
