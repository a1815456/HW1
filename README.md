# HW1 - HTTP Proxy Server (Python)

## Description

This project implements a simple HTTP proxy server in Python.

The server listens on a specified port, receives HTTP requests from clients,
forwards them to the origin server, caches the response locally, and sends it back to the client.
If the requested content is already cached, it serves the content directly from the cache.

## How to Run

Start the proxy server by running:

```bash
python Proxy.py localhost 8080
```

This starts the proxy on port 8080.

## How to Test

You can test the proxy server using the following curl commands:

###  Basic HTTP Request

```bash
curl -i http://localhost:8080/http://http.badssl.com/
```

Expected:
- First request goes to origin server
- Response is received and cached
- Status: HTTP/1.1 200 OK

###  Cache Hit Verification

Run the same curl command again:

```bash
curl -i http://localhost:8080/http://http.badssl.com/
```

Expected:
- Content served from local cache
- Output contains: "CACHE HIT!"

###  Cache File Created

You can verify the cache file exists:

```bash
ls ./http.badssl.com/
```

Expected:
- File named `default` or hash is present

## Features Implemented

-  HTTP GET request handling
-  Origin server communication
-  Response forwarding
-  Cache file writing
-  Cache lookup and serving
-  Informative terminal logging

## Student Info

Student ID: a1815456  
Course: Computer Systems - HW1 (HTTP Proxy Server)  
Submission: Python implementation with testing via curl

