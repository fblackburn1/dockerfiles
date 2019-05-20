FROM python:3.7-slim-stretch

ARG CLOUDFLARE_VERSION=2.1.0
ARG MARSHMALLOW_VERSION=3.0.0rc5
ARG RESPONDER_VERSION=1.3.0
LABEL responder-version=$CLOUDFLARE_VERSION
LABEL responder-version=$MARSHMALLOW_VERSION
LABEL responder-version=$RESPONDER_VERSION

RUN true \
    && apt-get update \
    && apt-get install --yes gcc \
    && pip install responder==$RESPONDER_VERSION \
    && pip install marshmallow==$MARSHMALLOW_VERSION \
    && pip install cloudflare==$CLOUDFLARE_VERSION \
    && apt-get purge --yes gcc \
    && apt-get autoremove --yes \
    && apt-get clean

COPY ./cloudflare-ddns-proxy /usr/local/src/cloudflare-ddns-proxy

CMD ["/usr/local/src/cloudflare-ddns-proxy"]
