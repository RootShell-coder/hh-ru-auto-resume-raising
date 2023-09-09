# Head hunter bot

![hh ru auto resume raising](https://github.com/RootShell-coder/hh-ru-auto-resume-raising/actions/workflows/docker-publish.yaml/badge.svg?branch=docker)

Many thanks

- [sergo-code](https://github.com/sergo-code) [hh-ru-auto-resume-raising](https://github.com/sergo-code/hh-ru-auto-resume-raising) python
- [mitetenov](https://github.com/mitetenov) [hh-ru-auto-resume-raising](https://github.com/mitetenov/hh-ru-auto-resume-raising) docker

## Correct values

```yml
phone=79876543210
password=qwerty123
proxy=None or http://login:password@ip:port
bot_token=1111111:a1a1a1a1a1a
admin_tg=01020304
time_zone=Europe/Moscow
```

**proxy None or your proxy server*

## Run docker compose

docker-compose.yaml

```yaml
version: '3.9'
services:
  hh:
    image: rootshellcoder/hh-ru-auto-resume-raising:latest
    restart: always
    env_file:
      - .env_pub
```
