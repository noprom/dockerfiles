FROM nginx:1.9.0

# Install env
ADD sources.list    /etc/apt/sources.list
RUN apt-get update && apt-get install -y \
        git \
        vim \
        libgearman-dev \
        libmemcached-dev \
        libmcrypt-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng12-dev \
        && rm -r /var/lib/apt/lists/*
        
ADD  nginx.conf      /etc/nginx/nginx.conf
ADD  sites-enabled/*    /etc/nginx/conf.d/
RUN  mkdir /app && mkdir /app/data && mkdir /app/domains && mkdir /app/www && mkdir /app/log && mkdir /app/log/nginx && mkdir /app/log/php
RUN  chown -R www-data.www-data /app/www /app/log

EXPOSE 80
VOLUME ["/app"]