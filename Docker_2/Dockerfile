FROM python:3.8

WORKDIR /app

COPY . /app

ENV DEBUG=False SECRET_KEY=secret_key

RUN pip install -r requirements.txt
RUN python manage.py migrate
RUN python manage.py collectstatic

EXPOSE 8000

CMD ["gunicorn", "stocks_products.wsgi", "-b", "0.0.0.0:8000"]


