# Spatio.Sdk.Model.NoteListEnvelope
Standard fan-out response for `GET /v1/notes`. Items aggregate notes across every connected account that contributed to the call; each contributing account contributes one `accounts[]` entry — including failed accounts, so the client can render which providers contributed and which errored without the call itself failing. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Items** | [**List&lt;Note&gt;**](Note.md) |  | 
**Accounts** | [**List&lt;AccountStatus&gt;**](AccountStatus.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

