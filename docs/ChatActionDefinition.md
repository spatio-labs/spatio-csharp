# Spatio.Sdk.Model.ChatActionDefinition
One entry in `GET /actions`. Action ids are dotted (e.g. `direct-messages.send`, `channels.list`); the `executeAction` endpoint accepts the id with a free-form `params` object. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Name** | **string** |  | 
**Description** | **string** |  | [optional] 
**Platform** | **string** |  | 
**Category** | **string** | Common values: &#x60;read&#x60;, &#x60;write&#x60;, &#x60;delete&#x60;, &#x60;manage&#x60;, &#x60;sync&#x60;. | [optional] 
**InputType** | **string** |  | [optional] 
**OutputType** | **string** |  | [optional] 
**Scopes** | **List&lt;string&gt;** | &#x60;null&#x60; when no scopes are declared (Go nil-slice). | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

