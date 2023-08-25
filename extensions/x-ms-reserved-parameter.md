# OpenAPI Extension: x-ms-reserved-parameter

This extension enables OpenAPI to convey additional information about the path parameters.

## x-ms-reserved-parameter property

## Property

This extension is a boolean property that defines whether a path parameter should be converted to a [reserved expansion parameter](https://www.rfc-editor.org/rfc/rfc6570#section-3.2.3) or not when building a RFC 6570 URI Template from the servers/path/parameters.

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-reserved-parameter` property.

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
  /foo/{bar}
    parameters:
      - in: path
        name: bar
        type: string
        required: true
        x-ms-reserved-parameter: true
servers:
  - url: https://graph.microsoft.com/v1.0
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)
