default: build

build:
	docker-compose -f ./build/standalone.yml build

run:
	docker-compose -f ./build/standalone.yml up -d

up:
	docker-compose -f ./build/standalone.yml up

down:
	docker-compose -f ./build/standalone.yml down

test:
	docker-compose -f ./build/standalone.yml run app sh -c "pytest $(TARGET)" --rm

command:
	docker-compose -f ./build/standalone.yml run app sh -c "python manage.py $(TARGET)" --rm

makemigrations:
	docker-compose -f ./build/standalone.yml run app sh -c "python manage.py makemigrations $(TARGET)" --rm

migrate:
	docker-compose -f ./build/standalone.yml run app sh -c "python manage.py migrate $(TARGET)" --rm
