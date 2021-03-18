default: build

DEV_COMPOSE_FILE_PATH = compose/standalone.yml
PROD_COMPOSE_FILE_PATH = compose/production.yml

COMPOSE_DEV = docker-compose -f $(DEV_COMPOSE_FILE_PATH)
COMPOSE_PROD = docker-compose -f $(PROD_COMPOSE_FILE_PATH)

OPTIONS = --rm

RUN_CMD_DEV = $(COMPOSE_DEV) run $(OPTIONS) devapp sh -c
RUN_CMD_PROD = $(COMPOSE_PROD) run $(OPTIONS) app sh -c


build:
	$(COMPOSE_DEV) build

run-dev: up

run-prod:
	$(COMPOSE_PROD) build
	$(COMPOSE_PROD) up -d

shutdown: down
shutdown-prod: 
	$(COMPOSE_PROD) down

up:
	$(COMPOSE_DEV) up

down:
	$(COMPOSE_DEV) down

lint:
	$(RUN_CMD_DEV) "flakehell lint"

test:
	$(RUN_CMD_DEV) "pytest --cov=./src --cov-config=./pyproject.toml $(TARGET)"

command:
	$(RUN_CMD_DEV) "python manage.py $(TARGET)"

migrations:
	$(RUN_CMD_DEV) "python manage.py makemigrations $(TARGET)"

migrate:
	$(RUN_CMD_DEV) "python manage.py migrate $(TARGET)"

migrate-prod:
	$(RUN_CMD_PROD) "python manage.py migrate $(TARGET)"
