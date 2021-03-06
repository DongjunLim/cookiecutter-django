FROM python:3.9-slim

RUN apt-get update && apt-get install -y g++ default-libmysqlclient-dev

COPY requirements.txt .
RUN pip install -r requirements.txt

ADD . /{{cookiecutter.project_name}}

WORKDIR /{{cookiecutter.project_name}}/src

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
