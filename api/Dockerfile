FROM python:3.8-slim

WORKDIR /srv

RUN pip install -U pip setuptools wheel

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY gunicorn.conf.py gunicorn.conf.py
COPY src src

ENTRYPOINT ["gunicorn", "-k", "uvicorn.workers.UvicornWorker", "src.main:app"]
