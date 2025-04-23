# OpenAPI Extension: x-ai-description

This extension enables OpenAPI to convey a description of the plugin that is provided to the AI model.

## x-ai-description property

This extension is a string property that contains the description for the plugin that is provided to the model. This description should describe what the plugin is for, and in what circumstances its functions are relevant. It is typically defined at the info level.

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ai-description` property.

```yaml
type: string
```

## Example

```yaml
openapi: 3.0.3
info:
  title: Weather Information API
  version: 1.0.0
  description: API for retrieving weather forecasts
  x-ai-description: "This plugin provides current weather conditions and forecasts for any location worldwide. Use it when the user asks about weather, temperature, precipitation, or atmospheric conditions for a specific location or wants to plan activities based on weather forecasts."
paths:
  /weather/{location}:
    get:
      operationId: getWeather
      parameters:
        - name: location
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: Weather information for the requested location
          content:
            application/json:
              schema:
                type: object
                properties:
                  location:
                    type: string
                  current:
                    type: object
                  forecast:
                    type: array
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)