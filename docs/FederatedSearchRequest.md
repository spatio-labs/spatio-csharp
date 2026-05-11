# Spatio.Sdk.Model.FederatedSearchRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Query** | **string** |  | 
**Platforms** | **List&lt;FederatedSearchRequest.PlatformsEnum&gt;** | Subset to fan out to. Empty means all available platforms. | [optional] 
**Limit** | **int** |  | [optional] [default to 25]
**PageTokens** | **Dictionary&lt;string, string&gt;** | Per-platform cursor for pagination. | [optional] 
**WorkspaceId** | **string** |  | [optional] 
**OrganizationId** | **string** |  | [optional] 
**IncludeShared** | **bool** |  | [optional] 
**IncludeArchived** | **bool** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

