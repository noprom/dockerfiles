FROM node:10.8.0-alpine
RUN apk add --update --no-cache \
  bash \
  git \
  g++ \
  gcc \
  libgcc \
  libstdc++ \
  linux-headers \
  alpine-sdk \
  make \
  && npm install -g migrate-mongo
CMD ["node"]
