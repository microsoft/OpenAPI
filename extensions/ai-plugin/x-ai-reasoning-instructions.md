# OpenAPI Extension: x-ai-reasoning-instructions

This extension enables defining reasoning instructions for operations in the OpenAPI document. These instructions guide AI models in how to reason about or execute the operation.

## x-ai-reasoning-instructions property

This extension is an array of string properties that provides instructions to guide the reasoning process when an AI model executes the operation. It can be defined at the operation level.

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ai-reasoning-instructions` property.

```yaml
type: array
items:
  type: string
```
## Example

```yaml
openapi: 3.0.3
info:
  title: Pet Store API
  description: A sample API for managing pets
  version: 1.0.0
paths:
  /pets:
    get:
      operationId: listPets
      description: Returns a list of pets
      x-ai-reasoning-instructions:
        - "Break down search by category first, then by status if specified"
        - "Filter results by age if the age parameter is provided"
        - "Order results by name alphabetically unless another ordering is specified"
      parameters:
        - name: category
          in: query
          description: The category of pets to return
          schema:
            type: string
        - name: status
          in: query
          description: The status of pets to return
          schema:
            type: string
      responses:
        '200':
          description: A list of pets
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/Pet'
components:
  schemas:
    Pet:
      type: object
      required:
        - id
        - name
      properties:
        id:
          type: integer
          format: int64
        name:
          type: string
        category:
          type: string
        status:
          type: string
```
Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)