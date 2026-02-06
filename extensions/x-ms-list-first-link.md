# OpenAPI Extension: x-ms-list-first-link

This extension marks a response property as the first-page link for a list operation, corresponding to the TypeSpec @firstLink decorator.

## Applies to

- Schema property (response body)

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-list-first-link` extension.

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
      responses:
        '200':
          description: List of items
          content:
            application/json:
              schema:
                type: object
                properties:
                  firstLink:
                    type: string
                    x-ms-list-first-link: true
```

Used by: (informational)

* [TypeSpec](https://typespec.io/)
