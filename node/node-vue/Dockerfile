FROM node:10.8.0-alpine
RUN apk add --update --no-cache --virtual .build-deps \
  bash \
  git \
  alpine-sdk \
  && apk del .build-deps
CMD [ "node"]