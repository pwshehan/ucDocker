FROM node:14.17.0-alpine

RUN apk add --update tini

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY package.json ./

RUN npm install

RUN npm cache clean --force

COPY . .

EXPOSE 80

CMD ["/sbin/tini", "--", "node", "./bin/www"]