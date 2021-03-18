# {{cookiecutter.project_name}}

## API Docs
```shell
# you need to run server before looking at the api docs.
$ make run-prod

# api urls
http://localhost/swagger
http://localhost/redoc
```

## Running the server
```shell
# run dev-server foreground
$ make run-dev

# run fake prod-server
# it's not real production server.
$ make run-prod

# stop all dev containers
$ make shutdown

# stop all prod containers
$ make shutdown-prod 
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
$ make migrations TARGET="specific_app"

# This is equivalent to "python manage.py migrate appname"
$ make migrate TARGET="specific_app"

# This command migrate to the production server
$ make migrate-prod TARGET="specific_app"
```
