# nextcloud-news-updater

Wrap the nextcloud-news-updater script inside an image.
See https://github.com/nextcloud/news-updater


## Configuration

* `NEXTCLOUD_URL`: The nextcloud url with a valid certificate (required)
* `NEXTCLOUD_USER`: The nextcloud user (required)
* `NEXTCLOUD_TOKEN`: The nextcloud user token/password (required)


## Build Image

`docker build -t fblackburn/nextcloud-news-updater --build-arg "NEXTCLOUD_NEWS_UPDATER_VERSION=11.0.0" .`
