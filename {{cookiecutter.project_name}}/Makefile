default: build

build:
	docker-compose build

run:
	docker-compose up -d

up:
	docker-compose up

down:
	docker-compose down

test:
	docker-compose run app sh -c "pytest ." --rm

migrate:
	docker-compose run app sh -c "python manage.py migrate" --rm
