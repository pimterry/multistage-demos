FROM node:8-alpine

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY ./built.js .

CMD [ "/usr/local/bin/node", "./built.js" ]