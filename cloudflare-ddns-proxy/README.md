# cloudflare-ddns-proxy

Image to proxy ddns mechanic with cloudflare api. The main reason of this proxy is to avoid to share
cloudflare API key to different zone. Some logic are inspired by [joshuaavalon][joshua-cloudflare]


## Configuration

* `CF_API_KEY`: Cloudflare API key (directly handled by [Cloudflare python client][cloudflare-python-client])
* `CF_API_EMAIL`: Cloudflare API email (directly handled by [Cloudflare python client][cloudflare-python-client])
* `API_LISTEN`: The listen address of the server (default: 0.0.0.0)
* `API_PORT`: the port of the server (default: 6789)
* `AUTHORIZATIONS`: A list of authorizations (`<zone_name>:<record_name>:<token>"`) to allow
  separate with comma. (example:
  `example.com:example.com:1a2b3c,example.com:toto.example.com:4d5e6f`)


## Usage

TODO


## TODO

* IPv6
* Autodetect IP address from host if no content


## Build Image

`docker build -t fblackburn/cloudflare-ddns-proxy --build-arg "RESPONDER_VERSION=1.3.0" .`


[cloudflare-python-client]: https://github.com/cloudflare/python-cloudflare
[joshua-cloudflare]: https://github.com/joshuaavalon/docker-cloudflare
