# ベースとなるイメージの指定
FROM php:7.4-apache

# 必要なパッケージのインストール
RUN apt-get update && apt-get install -y \
	libpng-dev \
	libonig-dev \
	libxml2-dev \
	zip \
	curl \
	unzip

# PHPの拡張モジュールのインストール
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# Composerのインストール
#COPY --from=composer /usr/bin/composer /usr/bin/composer

# アプリケーションのソースコードのコピー
#COPY . /var/www/html/

# ポートの公開
EXPOSE 80

# Apacheの設定
RUN a2enmod rewrite

# Apacheをフォアグラウンドで実行
CMD [ "apache2-foreground" ]
