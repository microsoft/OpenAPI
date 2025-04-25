# OpenAPI Extension: x-ai-capabilities

This extension enables defining plugin function capabilities in the OpenAPI document.

## x-ai-capabilities object

### Properties

The x-ai-capabilities object contains the following properties:

| name               | type                      | description                                                                                                            |
| ------------------ | ------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| confirmation       | Confirmation object       | Optional. Describes a confirmation dialog that SHOULD be presented to the user before invoking the function.           |
| response_semantics | Response semantics object | Optional. Describes how the orchestrator can interpret the response payload and provide a visual rendering.            |
| security_info      | Security info object      | Optional. Contains attestations about the behavior of the plugin in order to assess the risks of calling the function. |

### Confirmation object

| name  | type   | description                                                                            |
| ----- | ------ | -------------------------------------------------------------------------------------- |
| type  | string | Optional. Specifies the type of confirmation. Possible values are: None, AdaptiveCard. |
| title | string | Optional. The title of the confirmation dialog. This property is localizable.          |
| body  | string | Optional. The text of the confirmation dialog. This property is localizable.           |

### Response semantics object

| name            | type                                 | description                                                                                                       |
| --------------- | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| data_path       | string                               | Required. A JSONPath [RFC9535] query that identifies a set of elements from the function response to be rendered. |
| properties      | Response semantics properties object | Optional. Allows mapping of JSONPath queries to well-known data elements.                                         |
| static_template | object                               | Optional. A JSON object that conforms with the Adaptive Card Schema and templating language.                      |
| oauth_card_path | string                               | Optional.                                                                                                         |

### Response semantics properties object

| name                         | type   | description                                                                                       |
| ---------------------------- | ------ | ------------------------------------------------------------------------------------------------- |
| title                        | string | Optional. Title of a citation for the result.                                                     |
| subtitle                     | string | Optional. Subtitle of a citation for the result.                                                  |
| url                          | string | Optional. URL of a citation for the result.                                                       |
| thumbnail_url                | string | Optional. URL of a thumbnail image for the result.                                                |
| information_protection_label | string | Optional. Data sensitivity indicator of the result contents.                                      |
| template_selector            | string | Optional. A JSONPath expression to an Adaptive Card instance to be used for rendering the result. |

### Security info object

| name          | type            | description                                                                             |
| ------------- | --------------- | --------------------------------------------------------------------------------------- |
| data_handling | array of string | Required. An array of strings that describe the data handling behavior of the function. |


## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ai-capabilities` property.

```yaml
type: object
properties:
  confirmation:
    type: object
    properties:
      type:
        type: string
        enum: [None, AdaptiveCard]
      title:
        type: string
      body:
        type: string
  response_semantics:
    type: object
    required:
      - data_path
    properties:
      data_path:
        type: string
      properties:
        type: object
        properties:
          title:
            type: string
          subtitle:
            type: string
          url:
            type: string
          thumbnail_url:
            type: string
          information_protection_label:
            type: string
          template_selector:
            type: string
      static_template:
        type: object
      oauth_card_path:
        type: string
  security_info:
    type: object
    required:
      - data_handling
    properties:
      data_handling:
        type: array
        items:
          type: string
          enum: [GetPublicData, GetPrivateData, DataTransform, DataExport, ResourceStateUpdate]
```

## Example

```yaml
openapi: 3.0.3
info:
  title: Sample API with AI Capabilities
  version: 1.0.0
paths:
  /search:
    get:
      operationId: searchResources
      description: Search for resources
      x-ai-capabilities:
        confirmation:
          type: AdaptiveCard
          title: Confirm Search
          body: This will search across all resources. Continue?
        response_semantics:
          data_path: $.resources
          properties:
            title: $.name
            subtitle: $.location
            url: $.href
            information_protection_label: $.ipLabel
          static_template:
            $schema: "http://adaptivecards.io/schemas/adaptive-card.json"
            type: "AdaptiveCard"
            version: "1.5"
            body:
              - type: "TextBlock"
                text: "${name}"
                weight: "Bolder"
              - type: "TextBlock"
                text: "${description}"
            action:
              - type: "Action.OpenUrl"
                title: "View"
                text: "${href}"
        security_info:
          data_handling:
            - GetPrivateData
            - DataTransform
      responses:
        200:
          description: OK
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)