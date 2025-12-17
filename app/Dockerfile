FROM python:3.7-alpine

WORKDIR /code

RUN apk add --no-cache gcc musl-dev linux-headers

COPY requirements.txt /code/requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

COPY app.py /code/app.py

EXPOSE 80

CMD ["sh", "-c", "gunicorn -b 0.0.0.0:$PORT app:app"]
