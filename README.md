# Head hunter bot

![hh ru auto resume raising](https://github.com/RootShell-coder/hh-ru-auto-resume-raising/actions/workflows/docker-publish.yaml/badge.svg?branch=docker)

[github](https://github.com/sergo-code/hh-ru-auto-resume-raising)

docker-compose.yaml
```
version: '3.8'
services:

  hh:
    container_name: hh
    environment:
      PHONE: '79876543210'
      PASSWORD: 'qwerty123'
      PROXY: 'None'
      BOT_TOKEN: '1111111:a1a1a1a1a1a'
      ADMIN_TG: '01020304'
    image: rootshellcoder/hh-ru-auto-resume-raising:latest
    restart: unless-stopped
```
