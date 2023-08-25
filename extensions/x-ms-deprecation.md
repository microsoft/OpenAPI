# OpenAPI Extension: x-ms-deprecation

This extension enables API provides to convey additional details about the deprecation of any given API endpoint, schema, property, etc...

## x-ms-deprecation object

### Properties

Properties are optional unless specified otherwise.

| name | type | description |
|---|---|---|
| removalDate | DateTime | The date at which the element has been/will be removed entirely from the service. |
| date | DateTime | The date at which the element has been/will be deprecated. |
| version | String | The version this revision was introduced. |
| description | String | The description of the revision. |

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-deprecation` object.

```yaml
type: object
properties:
  removalDate:
    type: string
    format: date-time
    nullable: true
  date:
    type: string
    format: date-time
    nullable: true
  version:
    type: string
    nullable: true
  description:
    type: string
    nullable: true
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
        x-ms-deprecation:
          removalDate: '2022-10-24T00:00:00.0000000+00:00'
          date: '2022-08-30T00:00:00.0000000+00:00'
          version: 'v1.0'
          description: 'Foo APIs are being retired in favor of the bar APIs'
servers:
  - url: https://graph.microsoft.com/v1.0
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)
