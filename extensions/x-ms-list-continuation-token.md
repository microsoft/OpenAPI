# OpenAPI Extension: x-ms-list-continuation-token

This extension marks a continuation token used by list operations, corresponding to the TypeSpec @continuationToken decorator.

This extension MUST be set on both a request parameter and a response property.

## Applies to

- Parameter object (query parameter on an operation or path item)
- Schema property (response body)

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-list-continuation-token` extension.

```yaml
type: boolean
default: true
```

## Example

```yaml
openapi: 3.0.3
info:
  title: Example Service
  version: 1.0.0
paths:
  /items:
    get:
      parameters:
        - name: continuationToken
          in: query
          schema:
            type: string
          x-ms-list-continuation-token: true
      responses:
        '200':
          description: List of items
          content:
            application/json:
              schema:
                type: object
                properties:
                  continuationToken:
                    type: string
                    x-ms-list-continuation-token: true
```

Used by: (informational)

* [TypeSpec](https://typespec.io/)
