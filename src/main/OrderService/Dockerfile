FROM python:3.8-alpine

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

WORKDIR /app

COPY requirements.txt .

RUN apk add --no-cache --virtual .build-deps gcc musl-dev linux-headers && \
    pip install --no-cache-dir -r requirements.txt && \
    apk del .build-deps

COPY . .

CMD ["python", "app.py"]
