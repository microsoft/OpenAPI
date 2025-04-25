# OpenAPI Extension: x-ai-responding-instructions

This extension enables defining responding instructions for operations in the OpenAPI document. These instructions guide AI models in how to format or structure responses when communicating with users.

## x-ai-responding-instructions property

This extension is an array of string properties that provides instructions to guide the response formatting process when an AI model communicates results from the operation. It can be defined at the operation level.

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ai-responding-instructions` property.

```yaml
type: array
items:
  type: string
```

## Example

```yaml
openapi: 3.0.3
info:
  title: Weather API
  description: A sample API for accessing weather information
  version: 1.0.0
paths:
  /weather/current:
    get:
      operationId: getCurrentWeather
      description: Returns current weather information for a location
      x-ai-responding-instructions:
        - "Always include the temperature in both Celsius and Fahrenheit"
        - "Describe the weather conditions in a friendly, conversational manner"
        - "If air quality information is available, highlight any health concerns"
        - "When precipitation is expected, specify timing and intensity"
      parameters:
        - name: location
          in: query
          description: The location to get weather for
          required: true
          schema:
            type: string
      responses:
        '200':
          description: Current weather information
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/WeatherData'
components:
  schemas:
    WeatherData:
      type: object
      properties:
        location:
          type: string
        temperature:
          type: object
          properties:
            celsius:
              type: number
            fahrenheit:
              type: number
        conditions:
          type: string
        humidity:
          type: number
        windSpeed:
          type: number
        airQuality:
          type: string
        precipitation:
          type: object
          properties:
            probability:
              type: number
            type:
              type: string
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)