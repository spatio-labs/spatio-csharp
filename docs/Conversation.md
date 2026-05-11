# Spatio.Sdk.Model.Conversation
LLM conversation persisted by the platform-service. Stored in snake_case at the wire (legacy DTO; predates the camelCase rest of the API). Treat field names as authoritative. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**UserId** | **string** |  | 
**Title** | **string** |  | 
**Context** | **string** | Free-form context tag (e.g. &#x60;sidebar:sheets:entity:&lt;id&gt;&#x60;). | [optional] 
**Cwd** | **string** |  | [optional] 
**SessionId** | **string** |  | [optional] 
**Pinned** | **bool** |  | [optional] 
**LastMessageAt** | **DateTime?** |  | [optional] 
**MessageCount** | **int** |  | [optional] 
**IsActive** | **bool** |  | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**UpdatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

