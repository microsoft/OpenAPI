# OpenAPI Extensions used at Microsoft

## Extensions Supported in V2

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
|[x-ms-visibility](https://learn.microsoft.com/en-us/connectors/custom-connectors/openapi-extensions#x-ms-visibility)| visibility of parameters, operations, etc.| Power Platform & Logic Apps| |
|[x-ms-capabilities](https://learn.microsoft.com/en-us/connectors/custom-connectors/openapi-extensions#x-ms-capabilities)| connector level - testConnection capability, operation level - chunkTransfer | Power Platform & Logic Apps| |
|[x-ms-url-encoding](https://learn.microsoft.com/en-us/connectors/custom-connectors/openapi-extensions#x-ms-url-encoding)| Identifies whether the current path parameter should be double URL-encoded | Power Platform & Logic Apps| |
|[x-ms-dynamic-list](https://learn.microsoft.com/en-us/connectors/custom-connectors/openapi-extensions#use-dynamic-values)| describe parameters whose possible values are determined dynamically at runtime | Power Platform & Logic Apps| |
|[x-ms-dynamic-properties](https://learn.microsoft.com/en-us/connectors/custom-connectors/openapi-extensions#use-dynamic-schema)| describe schemas whose structure is determined dynamically at runtime | Power Platform & Logic Apps | |
|x-ms-connector-metadata| Key value pairs of metadata | Power Platform & Logic Apps | |
|[x-ms-pageable](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-pageable)| Pagination support for operations | Power Platform & Logic Apps| |
|x-ms-dynamic-tree| describe a schema or parameter whose values are dynamically retrieved and presented in a tree structure (e.g., file system) | Power Platform & Logic Apps | |
|x-ms-editor| Custom editor type for a property in UX | Power Platform & Logic Apps | |
|[x-ms-api-annotation](https://learn.microsoft.com/en-us/connectors/custom-connectors/openapi-extensions#x-ms-api-annotation)| operation versioning and lifecycle | Power Platform & Logic Apps | |

## Client Code Generation Extensions

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
|[x-ms-client-flatten](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-client-flatten) | flattens client model property or parameter. |AutoRest| |
|[x-ms-client-name](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-client-name) | allows control over identifier names used in client-side code generation for parameters and schema properties. |AutoRest| |
|[x-ms-code-generation-settings](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-code-generation-settings) | enables passing code generation settings via OpenAPI document |Autorest|  |
|[x-ms-deprecation](x-ms-deprecation.md)| Provides additional information about a deprecated endpoint, schema, property, etc... | Kiota | |
|[x-ms-enum-flags](x-ms-enum-flags.md)| Provides information about whether an enum is bitwise(flagged) and the expected serialization format | Kiota | |
|[x-ms-external](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-external) | allows specific Definition Objects to be excluded from code generation |AutoRest| |
|[x-ms-info-kiota](x-kiota-info.md)| Provides configuration information to the Kiota API client code generator| Kiota |
|[x-ms-mutability](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-mutability) | provides insight to Autorest on how to generate code. It doesn't alter the modeling of what is actually sent on the wire. |AutoRest| |
|[x-ms-odata](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-odata) | indicates the operation includes one or more [OData](http://www.odata.org/) query parameters. |AutoRest| |
|[x-ms-pageable](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-pageable) | allows paging through lists of data. |AutoRest||
|[x-ms-list](x-ms-list.md) | Marks an operation as a list operation. | TypeSpec | |
|[x-ms-list-page-index](x-ms-list-page-index.md) | Marks a query parameter as the page index for a list operation. | TypeSpec | |
|[x-ms-list-offset](x-ms-list-offset.md) | Marks a query parameter as the page offset for a list operation. | TypeSpec | |
|[x-ms-list-page-items](x-ms-list-page-items.md) | Marks a response property as the array of items for a list operation. | TypeSpec | |
|[x-ms-list-page-size](x-ms-list-page-size.md) | Marks a query parameter as the page size for a list operation. | TypeSpec | |
|[x-ms-list-next-link](x-ms-list-next-link.md) | Marks a response property as the next-page link for a list operation. | TypeSpec | |
|[x-ms-list-prev-link](x-ms-list-prev-link.md) | Marks a response property as the previous-page link for a list operation. | TypeSpec | |
|[x-ms-list-first-link](x-ms-list-first-link.md) | Marks a response property as the first-page link for a list operation. | TypeSpec | |
|[x-ms-list-last-link](x-ms-list-last-link.md) | Marks a response property as the last-page link for a list operation. | TypeSpec | |
|[x-ms-list-continuation-token](x-ms-list-continuation-token.md) | Marks a continuation token used by list operations. | TypeSpec | |
|[x-ms-parameter-grouping](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-parameter-grouping) | groups method parameters in generated clients |AutoRest| |
|[x-ms-parameter-location](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-parameter-location) | provides a mechanism to specify that the global parameter is actually a parameter on the operation and not a client property. |AutoRest| |
|[x-ms-primary-error-message](x-ms-primary-error-message.md) | provides a hint to which property to use in an error type as the error message. | Kiota | |
|[x-ms-reserved-parameter](x-ms-reserved-parameter.md) | provides details on whether a path parameter should be reserved in an URI template or not | Kiota | |
|[x-ms-sse-terminal-event](x-ms-sse-terminal-event.md) | provides a hint to indicate which streaming event is terminal | TypeSpec |

## AI Plugin Generation Extensions

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
|[x-ai-adaptive-card](ai-plugin/x-ai-adaptive-card.md) | Enables defining an external adaptive card for a given operation in the OpenAPI document. |Kiota| |
|[x-ai-auth-reference-id](ai-plugin/x-ai-auth-reference-id.md) | Provides a way to define the reference id of the auth registration to be used by the AI plugin. |Kiota| |
|[x-ai-capabilities](ai-plugin/x-ai-capabilities.md) | Provides a way to define the function capabilities of the AI plugin. |Kiota| |
|[x-ai-description](ai-plugin/x-ai-description.md) | Provides a way to define the description of the AI plugin that is provided to the AI model. |Kiota| |
|[x-ai-reasoning-instructions](ai-plugin/x-ai-reasoning-instructions.md) | Provides a way to define the reasoning instructions when invoking the plugin function. |Kiota| |
|[x-ai-responding-instructions](ai-plugin/x-ai-responding-instructions.md) | Provides a way to define the responding instructions when invoking the plugin function. |Kiota| |
|[x-legal-info-url](ai-plugin/x-legal-info-url.md) | Provides a way to define the URL for legal information the AI plugin. |Kiota| |
|[x-privacy-policy-url](ai-plugin/x-privacy-policy-url.md) | Provides a way to define the URL for privacy policy of the AI plugin. |Kiota| |

## UI Extensions

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
|x-ms-visibility| Determines the user facing visibility of the entity. The possible values are important, advanced and internal | Flow, Logic Apps | |
|x-ms-dynamic-values| |Flow, Logic Apps ||
|x-ms-dynamic-schema|This is a hint to the flow designer that the schema for this parameter or response is dynamic in nature.|Flow, Logic Apps| |

## Extending OpenAPI v3

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
| [x-ms-paths](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-paths) | alternative to Paths Object that allows Path Item Object to have query parameters |AutoRest, API Management| |
| [x-ms-discriminator-value](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-discriminator-value) | maps discriminator value on the wire with the definition name |AutoRest||
| [x-ms-enum](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-enum) | additional metadata for enums | AutoRest, Kiota| |

## Azure Specific extensions

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
| [x-ms-azure-resource](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-azure-resource) | indicates that the [Definition Schema Object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md#schemaObject) is a resource as defined by the [Resource Managemer API](https://msdn.microsoft.com/en-us/library/azure/dn790568.aspx) |AutoRest||
| [x-ms-request-id](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-request-id) | allows to overwrite the request id header name |AutoRest||
| [x-ms-client-request-id](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-client-request-id) | allows to overwrite the client request id header name |AutoRest||
| [x-ms-long-running-operation](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-long-running-operation) | indicates that the operation implemented Long Running Operation pattern as defined by the [Resource Managemer API](https://msdn.microsoft.com/en-us/library/azure/dn790568.aspx).|AutoRest||
|x-ms-export-notes | Notes about loss of API fidelity during export |API Management | |

## OpenAPI V2 extensions

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
| [x-ms-parameterized-host](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-parameterized-host) | replaces the OpenAPI host with a host template that can be replaced with variable parameters. |AutoRest||
| [x-ms-skip-url-encoding](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-skip-url-encoding)| skips URL encoding for path and query parameters |AutoRest| Support for unencoded query parameters in v3|
|x-ms-summary| Short plain text description used for parameters|Flow, Logic Apps, Functions| In V3 schema.title can be used instead |
|x-ms-servers|Support for identifying multiple API hosts|API Management| Temporary until official V3 `servers`|

## Extension Documentation

- [AutoRest Extensions]( https://github.com/Azure/autorest/blob/master/docs/extensions/readme.md)
- [PowerApps / Flow Extensions](https://flow.microsoft.com/en-us/documentation/customapi-how-to-swagger/)
