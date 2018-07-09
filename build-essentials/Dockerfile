FROM node:8.11.1-alpine

# Create app directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Install app dependencies
RUN apk update && apk upgrade && apk add git

ONBUILD COPY . /usr/src/app/

# https://github.com/mhart/alpine-node/issues/27#issuecomment-298395675
ONBUILD RUN apk add --no-cache --virtual .gyp make gcc g++ python && \
          rm -rf node_modules && \
          npm install --silent && \
          apk del .gyp make gcc g++ python

# Build app
ONBUILD RUN npm run build

ENV HOST 0.0.0.0
ENV NODE_ENV production
EXPOSE 3000

# start command
CMD [ "npm", "start" ]
