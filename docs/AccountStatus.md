# Spatio.Sdk.Model.AccountStatus
Outcome of one connected account's contribution to a fan-out call. Every connection that participated appears in `Envelope.accounts` exactly once, regardless of whether it succeeded, errored, or returned zero items. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Provider** | **string** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;, &#x60;google-keep&#x60;). | 
**AccountId** | **string** | Connected-account row id. | 
**AccountName** | **string** | Human-readable label for the account, when available. | [optional] 
**Status** | **string** | - &#x60;ok&#x60; — provider call returned without error. - &#x60;error&#x60; — provider call failed; details in &#x60;error&#x60;. - &#x60;skipped&#x60; — connection was filtered out before the provider   call ran. Reserved; not currently emitted by the runtime.  | 
**Error** | [**AccountError**](AccountError.md) |  | [optional] 
**NextPageToken** | **string** | Provider-specific cursor for the next page, if any. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

