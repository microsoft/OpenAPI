# OpenAPI Extension: x-privacy-policy-url

This extension enables OpenAPI to convey the URL for the privacy policy related to the plugin.

## x-privacy-policy-url property

This extension is a string property that contains an absolute URL that locates a document containing the privacy policy for the plugin. This property is localizable. It is typically defined at the info level.

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-privacy-policy-url` property.

```yaml
type: string
format: uri
```

## Example

```yaml
openapi: 3.0.3
info:
  title: User Data API
  version: 1.0.0
  description: API for accessing user profile information
  x-privacy-policy-url: "https://example.com/privacy-policy"
```

Used by: (informational)

* [Microsoft Kiota](https://aka.ms/kiota)