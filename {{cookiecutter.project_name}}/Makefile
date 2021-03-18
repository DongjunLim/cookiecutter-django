default: build

DEV_COMPOSE_FILE_PATH = compose/standalone.yml
PROD_COMPOSE_FILE_PATH = compose/production.yml

COMPOSE_DEV = docker-compose -f $(DEV_COMPOSE_FILE_PATH)
COMPOSE_PROD = docker-compose -f $(PROD_COMPOSE_FILE_PATH)

OPTIONS = --rm

RUN_CMD = $(COMPOSE_DEV) run $(OPTIONS) app sh -c


build:
	$(COMPOSE_DEV) build

run-dev: up

run-prod:
	$(COMPOSE_PROD) build
	$(COMPOSE_PROD) up -d

up:
	$(COMPOSE_DEV) up

down:
	$(COMPOSE_DEV) down

lint:
	$(RUN_CMD) "flakehell lint"

test:
	$(RUN_CMD) "pytest --cov=./src --cov-config=./pyproject.toml $(TARGET)"

command:
	$(RUN_CMD) "python manage.py $(TARGET)"

migrations:
	$(RUN_CMD) "python manage.py makemigrations $(TARGET)"

migrate:
	$(RUN_CMD) "python manage.py migrate $(TARGET)"
