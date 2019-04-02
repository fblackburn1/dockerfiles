# nextcloud-api

Image to expose nextcloud configuration through a REST API.

## Configuration

* `API_LISTEN`: The listen address of the server (default: 0.0.0.0)
* `API_PORT`: the port of the server (default: 6789)
* `NEXTCLOUD_PATH`: The path where your nextcloud is mounted inside your container (default: /var/www/html)


## Usage

### Maintenance

To enable or disable the maintenance mode of nextcloud:

`curl -X PUT -H "Accept: application/json" -H "Content-Type: application/json" -d "{"enabled": true}" http://nextcloud-api:6789/api/maintenance`


## Build Image

`docker build -t fblackburn/nextcloud-api --build-arg "RESPONDER_VERSION=1.3.0" .`
