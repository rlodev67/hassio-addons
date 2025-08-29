# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM=ghcr.io/hassio-addons/base-python:eb04110
FROM ${BUILD_FROM}

# Setup base
RUN apk add --no-cache python3 py3-pip

# workgroup folder
WORKDIR /app

ADD https://github.com/rlodev67/tydom2mqtt/archive/refs/heads/master.tar.gz /tmp/master.tar.gz
RUN tar -xzf /tmp/master.tar.gz --strip-components=1 -C /app

WORKDIR /app/app

RUN pip3 install --no-cache-dir -r requirements.txt

CMD ["python3", "-u", "/app/app/main.py"]

