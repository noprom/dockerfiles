FROM alpine:3.8

RUN	apk update && apk add libcap && \
    apk add ca-certificates wget && \
    update-ca-certificates && \
    rm -rf /var/cache/apk/*