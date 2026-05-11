# Spatio.Sdk.Model.ReplyEmailRequest
Reply to a specific email. `to/cc/bcc` are optional — the platform falls back to the original sender / recipients when omitted. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** |  | [optional] 
**To** | **List&lt;string&gt;** |  | [optional] 
**Cc** | **List&lt;string&gt;** |  | [optional] 
**Bcc** | **List&lt;string&gt;** |  | [optional] 
**Body** | **string** |  | 
**Html** | **bool** |  | [optional] 
**Attachments** | [**List&lt;AttachmentInput&gt;**](AttachmentInput.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

