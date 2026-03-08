# OpenAPI Extension: x-ai-adaptive-card

This extension enables defining an external adaptive card for a given operation in the OpenAPI document.

## x-ai-adaptive-card object

### Properties
Properties are required unless specified otherwise.

| name        | type     | description                                                                       |
| ----------- | -------- | --------------------------------------------------------------------------------- |
| data_path   | string   | A JSONPath [RFC9535][] query that identifies a set of elements from the function response to be rendered using the template specified in each item. |
| file        | string   |  Path to an external adaptive card file                                           |

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ai-adaptive-card` property.

```yaml
type: object
properties:
  data_path:
    type: string
    nullable: false
  file:
    type: string
    nullable: false
  title:
    type: string
    nullable: false
  url:
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
  /emails:
    get:
      operationId: searchEmails
      description: search for emails
      x-ai-adaptive-card:
        data_path: $.items
        file: path_to_file_for_email
        title: title
        url: url
      parameters:
        # Add parameters here
      responses:
        200:
          description: OK
  /chats:
    get:
      operationId: searchChats
      description: search for chats
      x-ai-adaptive-card:
        data_path: $.chats
        file: path_to_file_for_chat
        title: title
        url: url
      responses:
        200:
          description: OK

```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)
