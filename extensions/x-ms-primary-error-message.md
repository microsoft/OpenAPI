# OpenApi Extension: x-ms-primary-error-message

This extension allows API provider to indicate which property of an error types is the message to use for exceptions/errors. Any schema MUST NOT contain more than one instance of that extension with a value set to true, this includes any sub-schema associated to properties of a root schema. This extension MUST ONLY be used on properties or responses of type string.

## x-ms-primary-error-message extension

This extension is a singled value boolean (default false).

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-primary-error-message` object.

```yaml
type: boolean
```

## Example

```yaml
openapi: 3.0.3
info:
  title: OData Service for namespace microsoft.graph
  description: This OData service is located at https://graph.microsoft.com/v1.0
  version: 1.0.1
paths:
  /foo:
    get:
      responses:
        '404':
          content:
            application/json:
              schema:
                type: object
                properties:
                  bar:
                    type: string
                  errorMessage:
                    type: string
                    x-ms-primary-error-message: true
servers:
  - url: https://graph.microsoft.com/v1.0
```
