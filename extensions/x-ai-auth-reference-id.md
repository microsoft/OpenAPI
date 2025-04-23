# OpenAPI Extension: x-ai-auth-reference-id

This extension enables OpenAPI to convey the reference id of the auth registration to be used by a copilot plugin.

## x-ai-auth-reference-id property

## Property

This extension is a string property that contains the reference id of the auth registration. It must be defined within a security scheme object.

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ai-auth-reference-id` property.

```yaml
type: string
```

## Example

```yaml
openapi: 3.0.3
info:
  title: OData Service for namespace microsoft.graph
  description: This OData service is located at https://graph.microsoft.com/v1.0
  version: 1.0.1
paths:
  /users:
    get:
      operationId: getUsers
      parameters: []
      responses:
        '200':
          description: The request has succeeded.
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/User'
      security:
        - GraphOAuth2AuthAppOnly:
            - user.read.all
components:
  schemas:
    User:
      type: object
      required:
        - id
        - displayName
      properties:
        id:
          type: string
        displayName:
          type: string
  securitySchemes:
    GraphOAuth2AuthAppOnly:
      type: oauth2
      flows:
        clientCredentials:
          tokenUrl: https://login.microsoftonline.com/tenantid/oauth2/v2.0/token
          scopes:
            user.read.all: Grants read access to all users' full profiles
      x-ai-auth-reference-id-: 'otherValue123'
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)
