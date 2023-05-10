FROM php:7.4-apache

# PHPの拡張機能をインストールする場合など、追加の設定をここに書く
RUN apt-get update && apt-get install -y \
	libicu-dev \
	&& docker-php-ext-configure intl \
	&& docker-php-ext-install intl
RUN docker-php-ext-install pdo_mysql

# Apacheのmod_rewriteを有効にする
RUN a2enmod rewrite

# Apacheの設定をカスタマイズする場合、ここに書く

COPY . /var/www/html/