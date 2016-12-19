FROM debian:jessie

RUN apt-get update \
	&& apt-get install -y \
		php5-cgi \
		php5 \
		php5-curl \
		php5-json \
		php5-mysql \
		php5-pgsql \
		php5-gd \
		php5-mcrypt \
		php5-xdebug \
	&& rm -rf /var/lib/apt/lists/*

RUN find /etc/php5/ -type f -exec sed -i 's/post_max_size\s*=.*/post_max_size=80M/g' {} \;
RUN find /etc/php5/ -type f -exec sed -i 's/upload_max_filesize\s*=.*/upload_max_filesize=80M/g' {} \;
RUN echo 'xdebug.max_nesting_level=200' >> /etc/php5/mods-available/xdebug.ini
