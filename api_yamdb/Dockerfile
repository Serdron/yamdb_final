FROM python:3.7-slim

WORKDIR /app 

COPY requirements.txt .

RUN pip3 install -r ./requirements.txt --no-cache-dir

COPY ./ .

WORKDIR api_yamdb

RUN python manage.py migrate --no-input

RUN python manage.py collectstatic --no-input

WORKDIR ..

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]
