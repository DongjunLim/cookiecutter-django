default: build

build:
	docker-compose -f compose/standalone.yml build

run:
	docker-compose -f compose/standalone.yml up -d

up:
	docker-compose -f compose/standalone.yml up

down:
	docker-compose -f compose/standalone.yml down

lint:
	docker-compose -f compose/standalone.yml run app sh -c "flake8 ." --rm

test:
	docker-compose -f compose/standalone.yml run app sh -c "pytest $(TARGET)" --rm

command:
	docker-compose -f compose/standalone.yml run app sh -c "python manage.py $(TARGET)" --rm

makemigrations:
	docker-compose -f compose/standalone.yml run app sh -c "python manage.py makemigrations $(TARGET)" --rm

migrate:
	docker-compose -f compose/standalone.yml run app sh -c "python manage.py migrate $(TARGET)" --rm
