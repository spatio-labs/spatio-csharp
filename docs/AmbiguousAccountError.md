# Spatio.Sdk.Model.AmbiguousAccountError
Returned when the caller's request matches more than one connected account and no `accountId` query param disambiguates which one to target. The `accounts` array enumerates the candidates so the client can prompt the user to pick. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Error** | **string** | Human-readable error message. | 
**Code** | **string** | Machine-readable error code. Stable across releases for the canonical codes (&#x60;ambiguous_account&#x60;, &#x60;no_notes_provider&#x60;, &#x60;note_not_found&#x60;). Absent for generic errors.  | [optional] 
**Accounts** | [**List&lt;AccountChoice&gt;**](AccountChoice.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

