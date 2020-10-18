FROM python:3.7-slim-buster

ARG NEXTCLOUD_NEWS_UPDATER_VERSION=11.0.0
LABEL nextcloud-news-updater-version=$NEXTCLOUD_NEWS_UPDATER_VERSION

RUN pip3 install nextcloud_news_updater==$NEXTCLOUD_NEWS_UPDATER_VERSION

COPY ./nextcloud-news-updater-wrapper /usr/local/src/nextcloud-news-updater-wrapper

CMD ["/usr/local/src/nextcloud-news-updater-wrapper"]
