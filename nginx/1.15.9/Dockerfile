FROM ubuntu:18.04

ENV NGINX_VERSION   1.16.0
ADD nginx.conf      /etc/nginx/nginx.conf

RUN wget https://nginx.org/download/nginx-${NGINX_VERSION}.tar.gz && \
	tar zxf nginx-${NGINX_VERSION}.tar.gz && \
	cd nginx-${NGINX_VERSION} && \
	./configure && \
	--sbin-path=/usr/local/bin/nginx && \
	--conf-path=/etc/nginx/nginx.conf && \
	--pid-path=/var/run/nginx.pid && \
	--with-http_ssl_module && \
	--with-stream && \
	make && sudo make install

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]