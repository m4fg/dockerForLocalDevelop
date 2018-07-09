FROM php:5.6-apache

RUN echo '\
log_errors = On\n\
error_log = /dev/stderr\n\
error_reporting = E_ALL\n\
date.timezone = "Asia/Tokyo"\n\
' >> /usr/local/etc/php/php.ini

RUN docker-php-ext-install mysql

RUN apt update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y ssmtp

RUN echo 'sendmail_path = "/usr/sbin/ssmtp -t"' > /usr/local/etc/php/conf.d/mail.ini

RUN echo "FromLineOverride=YES" >> /etc/ssmtp/ssmtp.conf \
 && echo "Mailhub=docker.for.mac.host.internal:25" >> /etc/ssmtp/ssmtp.conf

