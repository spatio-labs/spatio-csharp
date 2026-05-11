# Spatio.Sdk.Model.PasswordRequiredError
Returned by `GET /public/notes/{token}` when the note is password-protected. `requiresPassword` is always `true` in this response; `invalidPassword` is `true` only when a password was supplied and rejected. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Error** | **string** | Human-readable error message. | 
**Code** | **string** | Machine-readable error code. Stable across releases for the canonical codes (&#x60;ambiguous_account&#x60;, &#x60;no_notes_provider&#x60;, &#x60;note_not_found&#x60;). Absent for generic errors.  | [optional] 
**RequiresPassword** | **bool** |  | 
**InvalidPassword** | **bool** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

