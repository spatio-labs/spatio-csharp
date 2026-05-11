# Spatio.Sdk.Model.ApiError
Standard error envelope returned by 4xx and 5xx responses across the SpatioAPI. Some endpoints attach extra machine-readable fields (`code`, `accounts`, `requiresPassword`, etc.) — those are documented on the individual operation. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Error** | **string** | Human-readable error message. | 
**Code** | **string** | Machine-readable error code. Stable across releases for the canonical codes (&#x60;ambiguous_account&#x60;, &#x60;no_notes_provider&#x60;, &#x60;note_not_found&#x60;). Absent for generic errors.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

