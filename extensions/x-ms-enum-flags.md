# OpenAPI Extension: x-ms-enums-flags

This extension enables API providers to specify an enum as a bitwise(flagged) enum as well as the format of serialization of the multiple selected values.

## x-ms-enums-flags object

### Properties

Properties are optional unless specified otherwise.

| name | type | description |
|---|---|---|
| isFlags | boolean | Whether or not the enum is bitwise(flagged). Default is `false`(same as not specifying the extension) |

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-deprecation` object.

```yaml
type: object
properties:
  isFlags:
    type: boolean
    default: false
```

## Example

```yaml
openapi: 3.0.3
info:
  title: OData Service for namespace microsoft.graph
  description: This OData service is located at https://graph.microsoft.com/v1.0
  version: 1.0.1
paths:
  '/foo'
    operations:
      get:
servers:
  - url: https://graph.microsoft.com/v1.0
definitions:
  Microsoft.Graph.Feature:
    title: Feature
    enum:
      - Feature1
      - Feature2
      - Feature3
      - Feature4
    type: string
    x-ms-enum-flags:
      isFlags: true
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)
