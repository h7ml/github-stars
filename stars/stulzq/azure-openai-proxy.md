---
project: azure-openai-proxy
stars: 1353
description: Azure OpenAI Service Proxy. Convert OpenAI official API request to Azure OpenAI API request. Support GPT-4,Embeddings,Langchain. Adapter from OpenAI to Azure OpenAI.
url: https://github.com/stulzq/azure-openai-proxy
---

azure-openai-proxy
==================

English|中文

Azure OpenAI Service Proxy, convert OpenAI official API request to Azure OpenAI API request, support all models, support GPT-4,Embeddings.

> Eliminate the differences between OpenAI and Azure OpenAI, acting as a bridge connecting them, OpenAI ecosystem accesses Azure OpenAI at zero cost.

Verified support projects：

Name

Status

chatgpt-web

√

chatbox

√

langchain

√

ChatGPT-Next-Web

√

Get Start
---------

### Retrieve key and endpoint

To successfully make a call against Azure OpenAI, you'll need the following:

Name

Desc

Default

AZURE\_OPENAI\_ENDPOINT

This value can be found in the **Keys & Endpoint** section when examining your resource from the Azure portal. Alternatively, you can find the value in **Azure OpenAI Studio** > **Playground** > **Code View**. An example endpoint is: `https://docs-test-001.openai.azure.com/`.

N

AZURE\_OPENAI\_API\_VER

See here or Azure OpenAI Studio

2024-02-01

AZURE\_OPENAI\_MODEL\_MAPPER

This value will correspond to the custom name you chose for your deployment when you deployed a model. This value can be found under **Resource Management** > **Deployments** in the Azure portal or alternatively under **Management** > **Deployments** in Azure OpenAI Studio.

N

`AZURE_OPENAI_MODEL_MAPPER` is a mapping from Azure OpenAI deployed model names to official OpenAI model names. You can use commas to separate multiple mappings.

**Format：**

`AZURE_OPENAI_MODEL_MAPPER`: <OpenAI Model Name>=<Azure OpenAI deployment model name>

OpenAI Model Names: https://platform.openai.com/docs/models

Azure Deployment Names: **Resource Management** > **Deployments**

**Example:**

AZURE\_OPENAI\_MODEL\_MAPPER: gpt-3.5-turbo=gpt-35-turbo

API Key: This value can be found in the **Keys & Endpoint** section when examining your resource from the Azure portal. You can use either `KEY1` or `KEY2`.

### Proxy

**HTTP Proxy**

Env:

AZURE\_OPENAI\_HTTP\_PROXY=http://127.0.0.1:1087

**Socks5 Proxy**

Env:

AZURE\_OPENAI\_SOCKS\_PROXY=socks5://127.0.0.1:1080

### Use Docker

# config by environment 
docker run -d -p 8080:8080 --name=azure-openai-proxy \\
  --env AZURE\_OPENAI\_ENDPOINT=your\_azure\_endpoint \\
  --env AZURE\_OPENAI\_API\_VER=your\_azure\_api\_ver \\
  --env AZURE\_OPENAI\_MODEL\_MAPPER=your\_azure\_deploy\_mapper \\
  stulzq/azure-openai-proxy:latest

# config by file
docker run -d -p 8080:8080 --name=azure-openai-proxy \\
  -v /path/to/config.yaml:/app/config.yaml \\
  stulzq/azure-openai-proxy:latest

Call API:

curl --location --request POST 'localhost:8080/v1/chat/completions' \\
-H 'Authorization: Bearer <Azure OpenAI Key>' \\
-H 'Content-Type: application/json' \\
-d '{
    "max\_tokens": 1000,
    "model": "gpt-3.5-turbo",
    "temperature": 0.8,
    "top\_p": 1,
    "presence\_penalty": 1,
    "messages": \[
        {
            "role": "user",
            "content": "Hello"
        }
    \],
    "stream": true
}'

### Use ChatGPT-Next-Web

docker-compose.yml

version: '3'

services:
  chatgpt-web:
    image: yidadaa/chatgpt-next-web
    ports:
      - 3000:3000
    environment:
      OPENAI\_API\_KEY: <Azure OpenAI API Key>
      BASE\_URL: http://azure-openai:8080
      CODE: ""
      HIDE\_USER\_API\_KEY: 1
      HIDE\_BALANCE\_QUERY: 1
    depends\_on:
      - azure-openai
    links:
      - azure-openai
    networks:
      - chatgpt-ns

  azure-openai:
    image: stulzq/azure-openai-proxy
    ports:
      - 8080:8080
    environment:
      AZURE\_OPENAI\_ENDPOINT: <Azure OpenAI API Endpoint>
      AZURE\_OPENAI\_MODEL\_MAPPER: <Azure OpenAI API Deployment Mapper>
      # AZURE\_OPENAI\_MODEL\_MAPPER: gpt-4=gpt-4,gpt-3.5-turbo=gpt-35-turbo
      AZURE\_OPENAI\_API\_VER: "2024-02-01"
    networks:
      - chatgpt-ns

networks:
  chatgpt-ns:
    driver: bridge

### Use ChatGPT-Web

ChatGPT Web: https://github.com/Chanzhaoyu/chatgpt-web

Envs:

-   `OPENAI_API_KEY` Azure OpenAI API Key
-   `AZURE_OPENAI_ENDPOINT` Azure OpenAI API Endpoint
-   `AZURE_OPENAI_MODEL_MAPPER` Azure OpenAI API Deployment Name Mappings

docker-compose.yml:

version: '3'

services:
  chatgpt-web:
    image: chenzhaoyu94/chatgpt-web
    ports:
      - 3002:3002
    environment:
      OPENAI\_API\_KEY: <Azure OpenAI API Key>
      OPENAI\_API\_BASE\_URL: http://azure-openai:8080
      # OPENAI\_API\_MODEL: gpt-4
      AUTH\_SECRET\_KEY: ""
      MAX\_REQUEST\_PER\_HOUR: 1000
      TIMEOUT\_MS: 60000
    depends\_on:
      - azure-openai
    links:
      - azure-openai
    networks:
      - chatgpt-ns

  azure-openai:
    image: stulzq/azure-openai-proxy
    ports:
      - 8080:8080
    environment:
      AZURE\_OPENAI\_ENDPOINT: <Azure OpenAI API Endpoint>
      AZURE\_OPENAI\_MODEL\_MAPPER: <Azure OpenAI API Deployment Mapper>
      AZURE\_OPENAI\_API\_VER: "2024-02-01"
    networks:
      - chatgpt-ns

networks:
  chatgpt-ns:
    driver: bridge

Run:

docker compose up -d

### Use Config File

The configuration file supports different endpoints and API keys for each model.

config.yaml

api\_base: "/v1"
deployment\_config:
  - deployment\_name: "xxx"
    model\_name: "text-davinci-003"
    endpoint: "https://xxx-east-us.openai.azure.com/"
    api\_key: "11111111111"
    api\_version: "2024-02-01"
  - deployment\_name: "yyy"
    model\_name: "gpt-3.5-turbo"
    endpoint: "https://yyy.openai.azure.com/"
    api\_key: "11111111111"
    api\_version: "2024-02-01"
  - deployment\_name: "zzzz"
    model\_name: "text-embedding-ada-002"
    endpoint: "https://zzzz.openai.azure.com/"
    api\_key: "11111111111"
    api\_version: "2024-02-01"

By default, it reads `<workdir>/config.yaml`, and you can pass the path through the parameter `-c config.yaml`.

docker-compose:

azure-openai:
    image: stulzq/azure-openai-proxy
    ports:
      - 8080:8080
    volumes:
      - /path/to/config.yaml:/app/config.yaml
    networks:
      - chatgpt-ns
