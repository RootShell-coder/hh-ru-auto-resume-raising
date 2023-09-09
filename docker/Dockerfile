FROM python:alpine AS build
WORKDIR  /home/hh
RUN set eux; \
    apk add --update --no-cache \
    bash \
    git \
    sed \
    libxml2 \
    libxslt-dev \
    libffi-dev \
    build-base; \
    addgroup -S hh; \
    adduser -S hh -G hh -h /home/hh -s /bin/bash;
USER hh
RUN set eux; \
    git clone https://github.com/sergo-code/hh-ru-auto-resume-raising.git --branch main --depth 1 .; \
    sed -i 's/aiohttp==3.8.1/aiohttp==3.8.5/' requirements.txt; \
    rm .env_pub; \
    python3 -m pip install -r requirements.txt;

FROM python:alpine
WORKDIR  /home/hh
RUN set eux; \
    apk add --update --no-cache \
    libxml2 \
    libxslt-dev \
    libffi-dev \
    build-base; \
    addgroup -S hh; \
    adduser -S hh -G hh -h /home/hh -s /bin/ash;
USER hh
COPY --chown=hh:hh --from=build /home/hh .
ENTRYPOINT [ "python3" , "bot.py" ]
