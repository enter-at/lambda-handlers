# Quickstart

## Installation

To install the latest version of lambda-handlers simply run:

```bash
pip install lambda-handlers
```

If you are going to use validation, we have examples that work with
[Marshmallow](https://pypi.org/project/marshmallow/) or
[jsonschema](https://pypi.org/project/jsonschema/).

But you can adapt a LambdaHandler to use your favourite validation module.
Please share it with us or create an issue if you need any help with that.

By default the `http_handler` decorator makes sure of parsing the request body
as JSON, and also formats the response as JSON with:
    - an adequate statusCode,
    - CORS headers, and
    - the handler return value in the body.


## Basic ApiGateway Proxy Handler
```python
from lambda_handlers.handlers import http_handler

@http_handler()
def handler(event, context):
    return event['body']
```
