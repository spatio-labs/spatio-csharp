# Spatio.Sdk.Model.Agent
Stored agent configuration (system prompt + tool selection). User-defined agents and preconfigured agents share this shape. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Name** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**SystemPrompt** | **string** |  | [optional] 
**Tools** | **List&lt;string&gt;** |  | [optional] 
**Icon** | **string** |  | [optional] 
**Color** | **string** |  | [optional] 
**IsDefault** | **bool** |  | [optional] 
**IsPreconfigured** | **bool** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**UpdatedAt** | **DateTime** |  | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

