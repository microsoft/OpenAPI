# OpenAPI Extension: x-ms-kiota-info

This extension enables API providers to annotation their OpenAPI descriptions to simplify the use of [Kiota](https://microsoft.github.io/kiota) tooling. By providing this information in the OpenAPI description it is not necessary for API consumers to provide these parameters when generating API client code.  This allows the API provider to deliver a simple experience for developers to generate clients and can easily identify package dependencies that further enhance the experience with support for custom media types and authentication providers.

## x-ms-kiota-info object

The `x-ms-kiota-info`object is used to contain information used by the Kiota API client generator tooling. It can appear as a property in the root object of the OpenAPI document.

### Properties

Properties are optional unless specified otherwise.

| name | type | description |
|---|---|---|
| languagesInformation | map[string,languageInformation] | Map of language information used to configure Kiota API client code generation. Only key values that match one of the values used in the Kiota `--language` [parameter](https://microsoft.github.io/kiota/using.html#--language--l) will be used by Kiota. Keys are matched case insensitive.|

## languageInformation Object

For each programming language supported by the API, a `languageInformation` object describes the recommended properties values to use for generation and usage of the API client code.

### Properties

Properties are optional unless specified otherwise.

| name | type | description |
|---|---|---|
| className | string| The name to use for generated client class|
| namespace |string | The namespace to use for all the generated classes(where supported by the language writer).|
| mediaTypes | string[]| Array of strings identifying media types used to represent structured types.|
| dependencyInstallCommand | string | A template for a command to be used to install dependencies for use with the API|
| dependencies | package[]] | An array of packages that the generated client code is dependent on.|

## package Object

An object that represents a package dependency that is required for the generated client code.

### Properties

| name | type | description |
|---|---|---|
| name | string| *Required* Name of package|
| version | string| *Required* Version of the package |

## Schema

Below is a yaml representation of the JSON Schema that defines the shape of the `x-ms-kiota-info` object.

```yaml
type: object
properties:
  languagesInformation:
    type: object
    patternProperties:
      '*': 
        { $ref: "#/$defs/languageInformation"}
$defs:
  languageInformation:
    type: object
    properties:
      className: { type: string }
      namespace: { type: string }
      mediaType: { type: array, items: {type: string} }
      dependencyInstallCommand: { type: string }
      dependencies: { type: array, items: {$ref: "#/$defs/package"} }
  package:
    type: object
    properties:
      name: { type: string }
      version: { type: string }
```

## Example

```yaml
openapi: 3.0.3
info:
  title: OData Service for namespace microsoft.graph
  description: This OData service is located at https://graph.microsoft.com/v1.0
  version: 1.0.1
x-ms-kiota-info:
  languagesInformation:
    CSharp:
      className: graphClient
      namespace: Microsoft.Graph
      dependencyInstallCommand: dotnet add package {name} --version {version}
      dependencies:
        - name: Microsoft.Graph.Core
          version: 3.0.0
servers:
  - url: https://graph.microsoft.com/v1.0")
```

Used by: (informational)

* [Microsoft Kiota](https://microsoft.github.io/kiota)
