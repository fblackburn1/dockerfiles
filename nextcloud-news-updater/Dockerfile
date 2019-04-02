FROM python:3.7-stretch-slim

ARG NEXTCLOUD_NEWS_UPDATER_VERSION=10.0.1
LABEL nextcloud-news-updater-version=$NEXTCLOUD_NEWS_UPDATER_VERSION

RUN pip3 install nextcloud_news_updater==$NEXTCLOUD_NEWS_UPDATER_VERSION --install-option="--install-scripts=/usr/bin"

COPY ./nextcloud-news-updater-wrapper /usr/local/src/nextcloud-news-updater-wrapper

CMD ["/usr/local/src/nextcloud-news-updater-wrapper"]
