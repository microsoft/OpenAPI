# OpenAPI Extension: x-ms-list

This extension marks an operation as a list operation, corresponding to the TypeSpec @list decorator.

## Applies to

- Operation object

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-list` extension.

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
      x-ms-list: true
      responses:
        '200':
          description: List of items
```

Used by: (informational)

* [TypeSpec](https://typespec.io/)
