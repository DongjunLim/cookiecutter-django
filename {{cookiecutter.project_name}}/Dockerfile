FROM python:3.9-slim

COPY . /{{cookiecutter.project_name}}
WORKDIR {{cookiecutter.project_name}}

RUN ls
RUN pip install --no-cache -r requirements.txt

WORKDIR /{{cookiecutter.project_name}}/src

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]