# OpenAPI Extension: x-ms-list-page-size

This extension marks a query parameter as the page size for a list operation, corresponding to the TypeSpec @pageSize decorator.

## Applies to

- Parameter object (query parameter on an operation or path item)

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-list-page-size` extension.

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
        - name: pageSize
          in: query
          schema:
            type: integer
          x-ms-list-page-size: true
      responses:
        '200':
          description: List of items
```

Used by: (informational)

* [TypeSpec](https://typespec.io/)
