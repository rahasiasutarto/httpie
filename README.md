## HTTPie: cURL for humans

HTTPie is a CLI frontend for [python-requests](python-requests.org).


### Installation

    pip install httpie


### Usage

    httpie [flags] METHOD [header:value data-field-name=value]* URL

The default request `Content-Type` in `application/json` and data fields are automatically serialized as a JSON `Object`:

    httpie PATCH  name=John api.example.com/person/1

That will issue the following request:

    PATCH /person/1 HTTP/1.1
    User-Agent: HTTPie/0.1
    X-API-Token: 123
    Content-Type: application/json; charset=utf-8

    {"name": "John"}


The data to be sent can also be passed via `stdin`:

    httpie PUT X-API-Token:123 api.example.com/person/1 < person.json

The flags mirror many of the arguments you would use with `requests.request`. See `httpie -h` for more details.


### Screenshot

![httpie](https://github.com/jkbr/httpie/raw/master/httpie.png)
