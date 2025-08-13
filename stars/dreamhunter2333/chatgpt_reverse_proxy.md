---
project: chatgpt_reverse_proxy
stars: 28
description: Chatgpt reverse proxy based on Browser
url: https://github.com/dreamhunter2333/chatgpt_reverse_proxy
---

Chatgpt reverse proxy based on Browser
======================================

-   Chatgpt reverse proxy based on Browser
    -   Features and TODO
    -   Overview
    -   requirements
    -   RUN in docker
    -   RUN locally
    -   reference

Features and TODO
-----------------

-   support wgcf to unblock access denied
-   support all `backen-api`
-   support login and auto get `ACCESS_TOKEN`
-   support manually get `ACCESS_TOKEN`
-   support use `ACCESS_TOKEN`
-   support proxy
-   base on browser
-   Auto Click cloudflare checkbox
-   auto refersh access\_token when 403
-   support arm64,amd64
-   vnc password
-   auto login

Overview
--------

requirements
------------

-   network access to openai
-   openai account
-   500M Memory, you can enable swap on you server

RUN in docker
-------------

Options:

1.  set `auto_refersh_access_token=True`. Open `localhost:7900`, your can forward port 7900 to local by ssh, and login to `https://chat.openai.com/`, if you get 403 when run sometimes. please `localhost:7900` and check again. **Make sure the first tab of the browser is `https://chat.openai.com/`**
2.  set `ACCESS_TOKEN` in your requset header's `Authorization`

ssh -L 7900:localhost:7900  azure\_vm

UI use chatgpt-web-share

change `config.yaml`

# from
chatgpt\_base\_url: http://127.0.0.1:6060/api/
# to
chatgpt\_base\_url: http://chatgpt-reverse-proxy:8000/backend-api/

version: "3"

services:
  chatgpt-share:
    image: ghcr.io/moeakwak/chatgpt-web-share:latest
    container\_name: chatgpt-web-share
    restart: always
    ports:
      - 80:80
      - 8080:80
      # - 6060:6060
    depends\_on:
      chatgpt-reverse-proxy:
        condition: service\_healthy
    volumes:
      - ./data:/data
      - ./config.yaml:/app/backend/api/config/config.yaml
      - ./logs:/app/logs

  chatgpt-reverse-proxy:
    image: ghcr.io/dreamhunter2333/chatgpt\_reverse\_proxy:latest
    # if you use arm64
    # image: ghcr.io/dreamhunter2333/chatgpt\_reverse\_proxy:arm64
    container\_name: chatgpt-reverse-proxy
    hostname: chatgpt-reverse-proxy
    restart: always
    ports:
      - "8000:8000"
      - "7900:7900"
    # if use auto\_refersh\_access\_token please mount tmp
    # volumes:
    #   - ./tmp:/app/tmp
    # if you ip is access denied, you can uncomment this to use wgcf
    # network\_mode: "service:wgcf"
    environment:
      - VNC\_NO\_PASSWORD=1
      # do not set VNC\_NO\_PASSWORD and you can set VNC\_PASSWORD
      # - VNC\_PASSWORD=password
      - user\_data\_dir=/app/tmp
      # - timeout=100000
      # - navigation\_timeout=100000
      # - proxy=http://127.0.0.1:7890
      # - auto\_refersh\_access\_token=False
    healthcheck:
      test:
        \[
          "CMD-SHELL",
          "curl --fail http://localhost:8000/health\_check || exit 1"
        \]
      interval: 30s
      timeout: 10s
      retries: 10

  # if you ip is access denied, you can uncomment this to use wgcf
  # wgcf:
  #   image: neilpang/wgcf-docker:latest
  #   volumes:
  #     - ./wgcf:/wgcf
  #     - /lib/modules:/lib/modules
  #   privileged: true
  #   sysctls:
  #     net.ipv6.conf.all.disable\_ipv6: 0
  #   cap\_add:
  #     - NET\_ADMIN
  #   command: "-4"

RUN locally
-----------

python3 -m venv ./venv
./venv/bin/python -m pip install -r requirements.txt
./venv/bin/playwright install
./venv/bin/python server.py
./venv/bin/python main.py

build docker image

docker compose buid
docker compose push
docker buildx build --platform linux/amd64 . --file Dockerfile --tag ghcr.io/dreamhunter2333/chatgpt\_reverse\_proxy:latest --push
docker buildx build --platform linux/arm64 . --file Dockerfile --tag ghcr.io/dreamhunter2333/chatgpt\_reverse\_proxy:arm64 --push

reference
---------

-   moeakwak/chatgpt-web-share
-   SeleniumHQ/docker-selenium
-   microsoft/playwright-python
-   Neilpang/wgcf-docker
