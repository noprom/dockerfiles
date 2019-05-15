FROM ubuntu:18.04

ENV NGINX_VERSION   1.16.0
ADD nginx.conf      /usr/local/nginx/conf/nginx.conf
WORKDIR /app
RUN apt-get update && apt-get install -y wget build-essential && \
	wget ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/pcre-8.42.tar.gz && \
	tar -zxf pcre-8.42.tar.gz && cd pcre-8.42 && \
	./configure && make && make install && cd .. && \
	wget http://zlib.net/zlib-1.2.11.tar.gz && \
	tar -zxf zlib-1.2.11.tar.gz && cd zlib-1.2.11 && \
	./configure && make && make install && cd .. && \
	wget http://www.openssl.org/source/openssl-1.1.1b.tar.gz && \
	tar -zxf openssl-1.1.1b.tar.gz && cd openssl-1.1.1b && \
	./config --prefix=/usr && \
	make && make install && cd .. && \
	wget https://nginx.org/download/nginx-${NGINX_VERSION}.tar.gz && \
	tar zxf nginx-${NGINX_VERSION}.tar.gz && ls -al && \
	cd nginx-${NGINX_VERSION} && \
	./configure && \
	--with-pcre=${WORKDIRs}/pcre-8.42 && \
	--with-zlib=${WORKDIR}/zlib-1.2.11 && \
	--with-http_ssl_module && \
	--with-stream && \
	make && make install

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]