FROM golang:1.12.1-alpine
RUN apk update && \
	apk add git && \
	rm -rf /var/cache/apk/*

RUN go get -v github.com/Masterminds/glide