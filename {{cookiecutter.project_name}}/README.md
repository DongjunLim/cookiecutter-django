# {{cookiecutter.project_name}}

## API Docs
```shell
# you need to run server before looking at the api docs.
$ make up

# api urls
http://localhost/swagger
http://localhost/redoc
```

## Running the server
```shell
# run server background
$ make run

# run server foreground
$ make up

# stop all containers
$ make down
```

## Test
```shell
$ make test

# test specific case
$ make test TARGET="specific_app/module_name"
```

## Lint
```shell
$ make lint
```

## DB Migration
```shell
# This is equivalent to "python manage.py makemigrations appname"
$ make makemigrations TARGET="specific_app"

# This is equivalent to "python manage.py migrate appname"
$ make migrate TARGET="specific_app"
```
