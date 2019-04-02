FROM python:3.7-slim-stretch

ARG RESPONDER_VERSION=1.3.0
LABEL responder-version=$RESPONDER_VERSION

RUN true \
    && apt-get update \
    && apt-get install --yes gcc \
    && pip install responder==$RESPONDER_VERSION \
    && apt-get purge --yes gcc \
    && apt-get autoremove --yes \
    && apt-get clean

COPY ./nextcloud-api /usr/local/src/nextcloud-api

CMD ["/usr/local/src/nextcloud-api"]
