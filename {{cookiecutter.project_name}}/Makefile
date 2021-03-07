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
	docker-compose run app sh -c "pytest $(TARGET)" --rm

command:
	docker-compose run app sh -c "python manage.py $(TARGET)" --rm

makemigrations:
	docker-compose run app sh -c "python manage.py makemigrations $(TARGET)" --rm

migrate:
	docker-compose run app sh -c "python manage.py migrate $(TARGET)" --rm
