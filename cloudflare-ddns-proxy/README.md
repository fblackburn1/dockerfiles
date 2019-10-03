# cloudflare-ddns-proxy

NOTE: Since 30 august 2019, Cloudflare support API token which depreciate the purpose of this image

Image to proxy ddns mechanic with Cloudflare api. The main reason of this proxy is to avoid to share
Cloudflare API key to different zone. Some logic are inspired by [joshuaavalon][joshua-cloudflare]


## Configuration

* `CF_API_KEY` (required): Cloudflare API key (directly handled by [Cloudflare python client][cloudflare-python-client])
* `CF_API_EMAIL` (required): Cloudflare API email (directly handled by [Cloudflare python client][cloudflare-python-client])
* `AUTHORIZATIONS` (required): A list of authorizations (`<zone_name>:<record_name>:<token>"`) to allow
  separate with comma. (example:
  `example.com:example.com:1a2b3c,example.com:toto.example.com:4d5e6f`)
* `API_LISTEN`: The listen address of the server (default: 0.0.0.0)
* `API_PORT`: The port of the server (default: 6789)
* `DEBUG`: Activate the debug (default: false)
* `IP_HEADER`: The header to get when no content is provided and IP must be extracted automatically
  (default: X-Real-IP)


## Usage

```bash
curl -X PUT --header 'Content-Type: application/json' \
-d '{"name": "example.com", "record": {"name": "sub.example.com", "content": "123.123.123.123"}}' \
--header 'X-Auth-Token: 1a2b3c' \
"http://ddns-proxy.example.com/api/zones"
```


## TODO

* IPv6


## Build Image

`docker build -t fblackburn/cloudflare-ddns-proxy .`


[cloudflare-python-client]: https://github.com/cloudflare/python-cloudflare
[joshua-cloudflare]: https://github.com/joshuaavalon/docker-cloudflare
