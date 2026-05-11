# Spatio.Sdk.Model.Recommendation
Agent-authored proposal that surfaces on the home feed. Status transitions: `pending` → `accepted | dismissed | expired`. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**WorkspaceId** | **string** |  | [optional] 
**UserId** | **string** |  | [optional] 
**Kind** | **string** | Provider-tagged proposal kind (e.g. &#x60;note.draft&#x60;, &#x60;task.followup&#x60;). | [optional] 
**Title** | **string** |  | [optional] 
**Body** | **string** |  | [optional] 
**Status** | **string** |  | 
**Payload** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**UpdatedAt** | **DateTime** |  | [optional] 
**ExpiresAt** | **DateTime?** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

