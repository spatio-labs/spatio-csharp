# Spatio.Sdk.Model.InboxItem
A unified-feed item. Source-aware — `category` indicates which upstream platform (mail, dm, channel, mention, system) produced it; `id` is the inbox-item id (not the underlying message id). 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Category** | **string** |  | 
**Title** | **string** |  | [optional] 
**Snippet** | **string** |  | [optional] 
**Source** | **string** |  | [optional] 
**SourceId** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**IsRead** | **bool** |  | [optional] 
**IsMention** | **bool** |  | [optional] 
**Timestamp** | **DateTime** |  | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

