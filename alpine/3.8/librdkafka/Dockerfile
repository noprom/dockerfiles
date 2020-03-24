FROM noprom/alpine:3.8

RUN apk update && \
	apk add bash git alpine-sdk && \
	rm -rf /var/cache/apk/* && \
    git clone https://github.com/edenhill/librdkafka.git && \
    cd librdkafka && \
    ./configure --prefix /usr && \
    make && \
    make install
