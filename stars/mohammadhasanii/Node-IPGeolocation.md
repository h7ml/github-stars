---
project: Node-IPGeolocation
stars: 11
description: This is an Express project with an API to get information about an IP address by sending a POST request with the IP address in the body, and receiving detailed information about the IP address in response.
url: https://github.com/mohammadhasanii/Node-IPGeolocation
---

Node-IPGeolocation
==================

IP Info API is a web service that provides you with information about the details of an IP address by receiving the IP address through a POST request to the / route.

Getting Started
---------------

To use this API, first, clone the repository: git clone https://github.com/mohammadhasanii/Node-IPGeolocation ↗

1-npm install

2-run command "node app.js"

Request
-------

This will make a POST request to the root endpoint '/' with a JSON body containing the IP address to lookup.

POST /

{ "ip": "8.8.8.8" }

Response
--------

The API will return a JSON response with details about the IP address:

{
  "ip": "8.8.8.8",
  "city": "Mountain View",
  "region": "California",
  "country": "United States",
  "loc": "37.3860,-122.0838",
  "org": "AS15169 Google LLC",
  "postal": "94035"
}
