FROM python:3.9-slim

RUN apt-get update && apt-get install -y g++ default-libmysqlclient-dev

COPY requirements.txt .
RUN pip install -r requirements.txt

ADD . /{{cookiecutter.project_name}}

WORKDIR /{{cookiecutter.project_name}}/src

RUN python manage.py collectstatic

RUN chmod 751 wait-for-it.sh

EXPOSE 8000
