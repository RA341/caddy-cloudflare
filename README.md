# Caddy cloudflare

Unofficial Automated repositry to build the latest caddy image with cloudflare dns plugin.

docs: https://caddy.community/t/how-to-guide-caddy-v2-cloudflare-dns-01-via-docker/8007

## Usage
```
caddy:
    image: 'ras334/caddyflare:latest'
    restart: unless-stopped
    cap_add:
      - NET_ADMIN
    ports:
      - "80:80"
      - "443:443"
      - "443:443/udp"
    env_file:
      - caddy.env
    volumes:
      - ./Caddyfile:/etc/caddy/Caddyfile
      - ./caddy/site/:/srv
      - ./caddy/data/:/data
      - ./caddy/config/:/config
      - ./caddy/log:/var/log
```

Example caddy envfile

```
# cloudflare
EMAIL=example@eg.com
CLOUDFLARE_API_TOKEN=.....
ACME_AGREE=true
```
