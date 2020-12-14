# nextcloud-api

Image to expose nextcloud configuration through a REST API.

## Configuration

* `API_LISTEN`: The listen address of the server (default: 0.0.0.0)
* `API_PORT`: the port of the server (default: 6789)
* `NEXTCLOUD_PATH`: The path where your nextcloud is mounted inside your container (default: /var/www/html)


## Usage

### Maintenance

To enable or disable the maintenance mode of nextcloud:

```sh
curl -X PUT -H "Accept: application/json" -H "Content-Type: application/json" -d "{"enabled": true}" http://nextcloud-api:6789/api/maintenance
```


## Build Image

```sh
docker build -t fblackburn/nextcloud-api --build-arg "FASTAPI_VERSION=0.62.0" --build-args "UVICORN_VERSION=0.13.1" .
```
