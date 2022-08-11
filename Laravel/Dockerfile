# imagen de dockerhub que descargara
FROM php:7.4-fpm-alpine

# algunas configuraciones para que funcione el contenedor
RUN docker-php-ext-install pdo pdo_mysql

# instala composer en el contenedor
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# da permisos para editar los archivos en esta ruta del container
RUN chown -R www-data:www-data /var/www
RUN chmod 755 /var/www

WORKDIR /var/www/html

COPY . /var/www/html
RUN composer install

CMD php artisan serve --host=0.0.0.0 --port=8081

EXPOSE 8081
