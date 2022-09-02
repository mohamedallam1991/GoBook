---
title: Simple Http server

date: 2022-08-16
description: This article teaches you everything you need to know about Concurency in Golang
lead: Lets learn Golang Concurency, how to declare them and how to use them.
categories:
  - "WebApp"
tags:
  - "Golang"
  - "Beginner"

---

Go, is very productive, lets build a web server in 5 minutes.
<!--more-->


## Golang web app

```go
package main

import (
	"fmt"
	"log"
	"net/http"
)

const PORT = ":9876"

func main() {
	fmt.Printf("starting the server: %v\n", PORT)

	HomeRoute := http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
		fmt.Fprintf(w, "hello Web")
	})
	log.Fatal(http.ListenAndServe(PORT, HomeRoute))
}

```
Visit the url, on the port number, and you will print out `hello Web`
> Visit url localhost:9876

> hello Web

![append to a slice](img/golang-hello-web.png "append to a slice")

## Theory

Golang is packages has one called `net/http` it cnotains a few ways of creating the HTTP server.
To create a web server you need 2 things.
- The handler function, it compromises the route and the controller, You can simply implement the `Handler` interface. in a method. they act like handlers or controllers in other languages or frameworks. so it has a ResponseWriter and pointer to the HttpRequest.
- The server itself is created in the `ListenAndServe`, on the given address. This method requires the Handler. you provided.
