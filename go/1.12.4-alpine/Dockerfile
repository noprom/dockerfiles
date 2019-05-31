FROM golang:1.12.4-alpine
RUN apk update && \
	apk add git alpine-sdk && \
	rm -rf /var/cache/apk/*

RUN go get -v github.com/Masterminds/glide
