# ekballo-docker
Ekballo project containerization repository

## Prerequisites
- Must have [Docker Engine](https://docs.docker.com/desktop/install/linux-install/) installed and running.
- Must have [Docker Compose](https://docs.docker.com/compose/compose-file/) installed (for previous Docker versions).

## Initial Setup
- Clone this repository into the parent directory of [`chat-frontend`](https://github.com/viktorsheep/chat-frontend) and [`chat-backend`](https://github.com/viktorsheep/chat-backend).
- Pull the images from dockerhub:
```bash
$ docker pull myobandar/ekballo_chat_backend:latest
$ docker pull myobandar/ekballo_chat_frontend:latest
```
- Navigate into `/ekballo-docker/`
- Start the containers:
```bash
$ docker compose up -d
```
This will start 2 containers: `chat_frontend` and `chat_backend`.

## Chat-Frontend
- Exec into the chat_frontend container:
```bash
$ docker exec chat_frontend /bin/ash
```
- Install dependencies (One-time setup):
```bash
$ npm install
```
- Start the service:
```bash
$ npm start
```

## Chat-Backend
- Exec into the chat_backend container:
```bash
$ docker exec chat_backend /bin/ash
```
- Install dependencies (One-time setup):
```bash
$ composer install
```
- Start the service:
```bash
$ php -S 0.0.0.0:8000 -t public
```

