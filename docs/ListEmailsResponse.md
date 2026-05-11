# Spatio.Sdk.Model.ListEmailsResponse
List of emails across the selected accounts. `provider` is set on single-account calls; on fan-out it carries the value from the first contributing account (legacy behavior — clients should rely on the per-row `provider` field instead). 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Emails** | [**List&lt;Email&gt;**](Email.md) | &#x60;null&#x60; when there are no results (Go nil-slice serialization). Treat as equivalent to an empty array.  | [optional] 
**Total** | **int** |  | 
**NextPageToken** | **string** |  | [optional] 
**Provider** | **string** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

