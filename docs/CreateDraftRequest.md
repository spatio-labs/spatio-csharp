# Spatio.Sdk.Model.CreateDraftRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** |  | [optional] 
**To** | **List&lt;string&gt;** |  | [optional] 
**Cc** | **List&lt;string&gt;** |  | [optional] 
**Bcc** | **List&lt;string&gt;** |  | [optional] 
**Subject** | **string** |  | [optional] 
**Body** | **string** |  | [optional] 
**Html** | **bool** |  | [optional] 
**Attachments** | [**List&lt;AttachmentInput&gt;**](AttachmentInput.md) |  | [optional] 
**ThreadId** | **string** | Provider thread id — set when this draft is a reply, so the sent message lands inside the parent thread.  | [optional] 
**InReplyTo** | **string** |  | [optional] 
**References** | **List&lt;string&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

