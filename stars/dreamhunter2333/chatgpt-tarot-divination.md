---
project: chatgpt-tarot-divination
stars: 610
description: AI 算命，占卜，塔罗牌，姓名五格，周公解梦，生辰八字，梅花易数
url: https://github.com/dreamhunter2333/chatgpt-tarot-divination
---

chatgpt tarot divination
========================

-   chatgpt tarot divination
    -   AI 算命，占卜 功能
    -   下载 EXE 安装包
    -   Deploy by docker
    -   Local Run

AI 算命，占卜 功能
-----------

-   塔罗牌
-   生辰八字
-   姓名五格
-   周公解梦
-   起名
-   梅花易数
-   姻缘 @alongLFB

下载 EXE 安装包
----------

下载 exe

设置中指定 API BASE URL, API KEY, 然后在主页就可以正常使用了

Deploy by docker
----------------

services:
  chatgpt-tarot-divination:
    image: ghcr.io/dreamhunter2333/chatgpt-tarot-divination:latest
    container\_name: chatgpt-tarot-divination
    restart: always
    ports:
      - 8000:8000
    environment:
      - api\_key=sk-xxx
      # - api\_base=https://api.openai.com/v1 # optional
      # - model=gpt-3.5-turbo # optional
      # - rate\_limit=10/minute # optional
      # - user\_rate\_limit=600/hour # optional
      - github\_client\_id=xxx
      - github\_client\_secret=xxx
      - jwt\_secret=secret
      - ad\_client=ca-pub-xxx
      - ad\_slot=123

Local Run
---------

创建 `.env` 文件，填入如下内容, `api_key` 为必填项, 其余为可选项

api\_key=sk-xxxx
api\_base=https://api.openai.com/v1
github\_client\_id=xxx
github\_client\_secret=xxx
ad\_client=ca-pub-xxx
ad\_slot=123

RUN

cd frontend
pnpm install
pnpm build --emptyOutDir
cd ..
rm -r dist
cp -r frontend/dist/ dist
python3 -m venv ./venv
./venv/bin/python3 -m pip install -r requirements.txt
./venv/bin/python3 main.py
