
FROM php:7.4-apache 
# for more PHP version and tags, go to Docker hub https://hub.docker.com/_/php/tags

# Install PHP extension dependencies (if any)
#RUN apt-get update \
#    && apt-get -y --no-install-recommends install <package_name>

# Copy PHP configuration
# Edit docker/php.ini and customize it to your needs
COPY docker/php.ini /usr/local/etc/php/php.ini

# Copy custom command docker-php-pecl-install
COPY docker/docker-php-pecl-install /usr/local/bin/

# Install PHP extensions
RUN docker-php-ext-install mysqli 
RUN docker-php-ext-enable mysqli

# Install PECL extensions
#RUN docker-php-pecl-install <package_name-version> (versions available in PECL repository allowed)

# If you are using XDebug, this might be useful, if not, ignore it
# You additionally will have to customize docker/xdebug-ini-overrides.ini file to your needs
#RUN docker-php-pecl-install xdebug-2.5.4
#COPY docker/xdebug-ini-overrides.ini /usr/local/etc/php/conf.d/docker-php-pecl-xdebug.ini

# Configure Apache VHOSTS
#COPY docker/mysite.com.conf /etc/apache2/sites-available/mysite.com.conf
#RUN a2ensite <mysite.com.conf>

# Activate Apache modules
# RUN a2enmod <module>
RUN a2enmod rewrite
RUN service apache2 restart

# Set the workdir
WORKDIR /var/www/html