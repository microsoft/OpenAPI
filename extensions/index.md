# OpenAPI Extensions used at Microsoft

## Client Code Generation Extensions

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
|[x-ms-info-kiota](x-kiota-info.md)| Provides configuration information to the Kiota API client code generator| Kiota |
|x-ms-pageable | allows paging through lists of data. |AutoRest||
|x-ms-parameter-grouping | groups method parameters in generated clients |AutoRest|
|x-ms-parameter-location | provides a mechanism to specify that the global parameter is actually a parameter on the operation and not a client property. |AutoRest|
|x-ms-odata | indicates the operation includes one or more [OData](http://www.odata.org/) query parameters. |AutoRest|||
|x-ms-external | allows specific Definition Objects to be excluded from code generation |AutoRest| |
|x-ms-code-generation-settings | enables passing code generation settings via OpenAPI document |Autorest|  |
|[x-ms-client-name](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-client-name) | allows control over identifier names used in client-side code generation for parameters and schema properties. |AutoRest| |
|[x-ms-client-flatten](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-client-flatten) | flattens client model property or parameter. |AutoRest| |
|x-ms-mutability | provides insight to Autorest on how to generate code. It doesn't alter the modeling of what is actually sent on the wire. |AutoRest||

## UI Extensions

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
|x-ms-visibility| Determines the user facing visibility of the entity. The possible values are important, advanced and internal | Flow, Logic Apps | |
|x-ms-dynamic-values| |Flow, Logic Apps ||
|x-ms-dynamic-schema|This is a hint to the flow designer that the schema for this parameter or response is dynamic in nature.|Flow, Logic Apps| |

## Extending OpenAPI v3

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
|x-ms-paths  | alternative to Paths Object that allows Path Item Object to have query parameters |AutoRest, API Management| |
|x-ms-discriminator-value | maps discriminator value on the wire with the definition name |AutoRest||
|x-ms-enum | additional metadata for enums |AutoRest| |

## Azure Specific extensions

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
|x-ms-azure-resource | indicates that the [Definition Schema Object](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md#schemaObject) is a resource as defined by the [Resource Managemer API](https://msdn.microsoft.com/en-us/library/azure/dn790568.aspx) |AutoRest||
|[x-ms-request-id](https://github.com/Azure/autorest/blob/main/docs/extensions/readme.md#x-ms-request-id) | allows to overwrite the request id header name |AutoRest||
|x-ms-client-request-id | allows to overwrite the client request id header name |AutoRest||
|x-ms-long-running-operation | indicates that the operation implemented Long Running Operation pattern as defined by the [Resource Managemer API](https://msdn.microsoft.com/en-us/library/azure/dn790568.aspx).|AutoRest||
|x-ms-export-notes | Notes about loss of API fidelity during export |API Management | |

## OpenAPI V2 extensions

| Name | Purpose | Used By | Status |
|------|---------|---------|--------|
|x-ms-parameterized-host | replaces the OpenAPI host with a host template that can be replaced with variable parameters. |AutoRest||
|x-ms-skip-url-encoding| skips URL encoding for path and query parameters |AutoRest| Support for unencoded query parameters in v3|
|x-ms-summary| Short plain text description used for parameters|Flow, Logic Apps, Functions| In V3 schema.title can be used instead |
|x-ms-servers|Support for identifying multiple API hosts|API Management| Temporary until official V3 `servers`|

## Extension Documentation

- [AutoRest Extensions]( https://github.com/Azure/autorest/blob/master/docs/extensions/readme.md)
- [PowerApps / Flow Extensions](https://flow.microsoft.com/en-us/documentation/customapi-how-to-swagger/)
