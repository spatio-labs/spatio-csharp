# Spatio.Sdk.Model.Channel
A chat conversation. The same struct backs both group channels (`type: channel | private`) and direct-message threads (`type: im | mpim`); the `Channels` and `DirectMessages` HTTP surfaces filter on `type` to give each its dedicated URL space. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Provider** | **string** | Registered provider id (e.g. &#x60;slack&#x60;, &#x60;native-chat&#x60;).  | [optional] 
**AccountId** | **string** |  | [optional] 
**Name** | **string** |  | 
**Type** | **string** | Provider-specific. Common canonicals: &#x60;channel&#x60; and &#x60;private&#x60; (group channels), &#x60;im&#x60; (1:1 DM), &#x60;mpim&#x60; (group DM).  | 
**Description** | **string** |  | [optional] 
**Topic** | **string** |  | [optional] 
**IsMember** | **bool** |  | 
**IsArchived** | **bool** |  | 
**MemberCount** | **int** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

