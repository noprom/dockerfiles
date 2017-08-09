#FROM daocloud.io/library/node:7.8-onbuild
FROM node:8.2.1

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD ARG NODE_ENV
ONBUILD ENV NODE_ENV $NODE_ENV
ONBUILD COPY package.json /usr/src/app/
ONBUILD RUN npm install -g cnpm --registry=https://registry.npm.taobao.org
ONBUILD RUN cnpm install && cnpm cache clean --force
ONBUILD COPY . /usr/src/app
CMD [ "npm", "start" ]
EXPOSE 8090