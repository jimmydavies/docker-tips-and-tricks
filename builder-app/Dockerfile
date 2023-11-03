# The official PHP image
FROM php:7.4.2 as builder

# copy the Composer PHAR from the Composer image into the PHP image
COPY --from=composer:1.9.3 /usr/bin/composer /usr/bin/composer
COPY src composer.json /app/

WORKDIR /app

# show that both Composer and PHP run as expected
RUN composer install

############################################
#                                          #
# Create a new image without build deps    #
# and simply copy compiled code into it    #
#                                          #
############################################
FROM php:7.4.2 as application

COPY --from=builder /app /app/
