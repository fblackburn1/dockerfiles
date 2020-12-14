FROM python:3.7-slim-stretch

ARG FASTAPI_VERSION=0.62.0
ARG UVICORN_VERSION=0.13.1
LABEL fastapi-version=$FASTAPI_VERSION
LABEL uvicorn-version=$UVICORN_VERSION

RUN pip install fastapi==$FASTAPI_VERSION uvicorn==$UVICORN_VERSION

COPY ./nextcloud-api /usr/local/src/nextcloud-api

CMD ["/usr/local/src/nextcloud-api"]
