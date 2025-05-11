SERVER_DOCKER_COMPOSE = ./docker-compose.server.yml
CLIENT_DOCKER_COMPOSE = ./docker-compose.client.yml

DOCKER_COMPOSE = docker compose -f

server-build:
	$(DOCKER_COMPOSE) $(SERVER_DOCKER_COMPOSE) build

client-build:
	$(DOCKER_COMPOSE) $(CLIENT_DOCKER_COMPOSE) build

server-run:
	$(DOCKER_COMPOSE) $(SERVER_DOCKER_COMPOSE) up -d

client-run:
	$(DOCKER_COMPOSE) $(CLIENT_DOCKER_COMPOSE) up -d

redis-run:
	$(DOCKER_COMPOSE) ./docker-compose.redis.yml up -d

server-stop:
	$(DOCKER_COMPOSE) $(SERVER_DOCKER_COMPOSE) stop

client-stop:
	$(DOCKER_COMPOSE) $(CLIENT_DOCKER_COMPOSE) stop

redis-stop:
	$(DOCKER_COMPOSE) ./docker-compose.redis.yml stop

exec:
	docker exec -it -u root $(CONTAINER_NAME) /bin/bash

run: server-run client-run

build: server-build client-build

restart-all: server-stop client-stop server-run client-run
