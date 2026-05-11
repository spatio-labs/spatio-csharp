# Spatio.Sdk.Model.Email
A single email message. The `provider`/`accountId` provenance fields tell clients which connected mail account this row came from (Gmail, Outlook, etc.) so multi-account list responses can be merged sensibly client-side. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**ThreadId** | **string** |  | [optional] 
**Provider** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**Subject** | **string** |  | 
**From** | **string** |  | 
**To** | **List&lt;string&gt;** |  | 
**Cc** | **List&lt;string&gt;** |  | [optional] 
**Bcc** | **List&lt;string&gt;** |  | [optional] 
**Body** | **string** |  | 
**Html** | **bool** | &#x60;true&#x60; when &#x60;body&#x60; contains HTML, &#x60;false&#x60; for plain text.  | 
**Date** | **DateTime** |  | 
**Labels** | **List&lt;string&gt;** |  | [optional] 
**IsRead** | **bool** |  | 
**IsStarred** | **bool** |  | 
**Attachments** | [**List&lt;AttachmentMeta&gt;**](AttachmentMeta.md) |  | [optional] 
**Snippet** | **string** |  | [optional] 
**MessageId** | **string** | RFC 5322 Message-ID header. | [optional] 
**InReplyTo** | **string** | RFC 5322 In-Reply-To header — the parent message id this message is a reply to.  | [optional] 
**References** | **List&lt;string&gt;** | RFC 5322 References header (ancestor chain). | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

