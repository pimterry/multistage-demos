FROM node:8 AS build

ARG NPM_TOKEN
RUN echo "//registry.npmjs.org/:_authToken=$NPM_TOKEN" >> ~/.npmrc && \
    npm whoami

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY . .
RUN npm install && npm run build

CMD [ "/usr/local/bin/node", "./built.js" ]

FROM node:8-alpine

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY --from=build /usr/src/app/built.js .

CMD [ "/usr/local/bin/node", "./built.js" ]