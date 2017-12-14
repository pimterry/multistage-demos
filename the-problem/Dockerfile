FROM node:8

ARG NPM_TOKEN
RUN echo "//registry.npmjs.org/:_authToken=$NPM_TOKEN" >> ~/.npmrc && \
    npm whoami

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY . .
RUN npm install && npm run build && rm ~/.npmrc

CMD [ "/usr/local/bin/node", "./built.js" ]