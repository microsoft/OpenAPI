# OpenAPI Extension: x-ms-enums-flags

This extension enables API providers to specify an enum as a bitwise(flagged) enum as well as the format of serialization of the multiple selected values.

## x-ms-enums-flags object

### Properties

Properties are optional unless specified otherwise.

| name | type | description |
|---|---|---|
| isFlags | boolean | Whether or not the enum is bitwise(flagged). Default is `false`(same as not specifying the extension) |
| style | string | The serialization format of the selected enum values. Default is `simple` |

#### `style` values

Only `simple`(Simple style parameters defined by [RFC6570](https://spec.openapis.org/oas/v3.0.0#style-values)) is currently supported by Kiota.

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-deprecation` object.

```yaml
type: object
properties:
  isFlags:
    type: boolean
    default: false
  style:
    type: string
    nullable: true
    default: simple
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
      style: simple
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)
