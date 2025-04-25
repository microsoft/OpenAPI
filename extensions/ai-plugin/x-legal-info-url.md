# OpenAPI Extension: x-legal-info-url

This extension enables OpenAPI to convey the URL for legal information related to the plugin.

## x-legal-info-url property

This extension is a string property that contains an absolute URL that locates a document containing the terms of service for the plugin. This property is localizable. It is typically defined at the info level.

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-legal-info-url` property.

```yaml
type: string
format: uri
```

## Example

```yaml
openapi: 3.0.3
info:
  title: File Storage API
  version: 1.0.0
  description: API for managing files in cloud storage
  x-legal-info-url: "https://example.com/terms-of-service"
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)