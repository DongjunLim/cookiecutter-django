default: build

COMPOSE_FILE_PATH = compose/standalone.yml
COMPOSE = docker-compose -f $(COMPOSE_FILE_PATH)
OPTIONS = --rm
RUN_CMD = $(COMPOSE) run $(OPTIONS) app sh -c

build:
	$(COMPOSE) build

run:
	$(COMPOSE) up -d

up:
	$(COMPOSE) up

down:
	$(COMPOSE) down

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
