FROM node:17-alpine

ARG TZ=UTC
ENV TZ=Asia/Yangon

RUN mkdir -p /usr/src/chat-frontend

WORKDIR /usr/src/chat-frontend

RUN apk update && apk upgrade && \
    apk add --no-cache python3 make g++

COPY package*.json /usr/src/chat-frontend/

RUN npm install

RUN npm run build