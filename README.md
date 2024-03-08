# Spring AI with Ollama

This project contains a web service that will accept HTTP GET requests at
`http://localhost:8080/ai/simple`.

There is optional `message` parameter whose default value is "Tell me a joke".

The response to the request is from the Ollama Mistral AI Service.

## Prerequisites

The application relies on [Ollama](https://ollama.ai) for providing LLMs. You can run Ollama locally on your laptop (macOS or Linux).

First, make sure you have [Ollama](https://ollama.ai) installed on your laptop (macOS or Linux).

```
ollama start
```

Then, use [Ollama](https://ollama.ai) to run the [mistral](https://ollama.com/library/mistral) large language model (default for Spring AI Ollama starter).

```
ollama run mistral
```

## Building and running

```
./mvnw spring-boot:run
```

## Access the endpoint

To get a response to the default request of "Tell me a joke"

```shell 
curl localhost:8080/ai/simple
```

A sample response is 

```text
Sure, here's a classic one for you:

Why don't scientists trust atoms?

Because they make up everything!
```

Now using the `message` request parameter
```shell
curl --get  --data-urlencode 'message=Tell me a joke about a cow.' localhost:8080/ai/simple 
```

A sample response is

```text
Why did the cow go to space?

Because it wanted to see the mooooon!
```

Alternatively use the [httpie](https://httpie.io/) client
```shell
http localhost:8080/ai/simple message=='Tell me a joke about a cow.'
```
