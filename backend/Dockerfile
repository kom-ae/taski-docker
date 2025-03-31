# FROM python:3.9
# ENV http_proxy 192.168.12.111:3130
FROM python:3.9-slim

WORKDIR /app

RUN pip install gunicorn==20.1.0

COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

COPY . .

# RUN python manage.py migrate

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]