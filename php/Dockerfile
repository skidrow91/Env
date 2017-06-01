From ubuntu:17.04
Run apt-get update && \
	apt-get install -y sudo && \
	apt-get install -y apt-utils && \
	apt-get install -y python-software-properties && \
	apt-get install -y software-properties-common && \
	LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php && \	
	apt-get install -y php && \
	apt-get install -y vim && \
	apt-get install -y apache2 && \
	apt-get install -y zip unzip php7.0-zip
Run php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
	php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
	php composer-setup.php && \
	php -r "unlink('composer-setup.php');"
#Run useradd -ms /bin/bash hvd
#USER hvd	
Run mv composer.phar /usr/local/bin/composer	
#Run composer global require "laravel/installer"	
RUN usermod -u 1000 www-data
EXPOSE 80
WORKDIR /var/www/html