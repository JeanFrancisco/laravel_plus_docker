FROM php:7.4-fpm

ARG user
ARG uid

# Install system-dependencies
RUN apt-get update && apt-get install -y \
    zip \
    curl \
    libpng-dev \
    libxml2-dev \
    openssl

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install PHP extensions
RUN docker-php-ext-install pdo_mysql \
    exif bcmath \
    pcntl gd \
    json

RUN pecl install xdebug && docker-php-ext-enable xdebug

# Get copy of the official composer image from the Docker Hub
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Add system user for laravel app
RUN useradd -G www-data,root -u $uid -d /home/$user $user
RUN mkdir -p /home/$user/.composer

# Change the user who owns the folder to 
# grant the directory permission
RUN chown -R $user:$user /home/$user

# Change the current user to
# the newly created one
USER $user

# Set working directory
WORKDIR /var/www

# OPTIONAL.
# By default the image already
# contains these configuration
# commands
EXPOSE 80
CMD ["php-fpm"]