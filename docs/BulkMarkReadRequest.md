# Spatio.Sdk.Model.BulkMarkReadRequest
Bulk shorthand for setting read state on many messages at once. `messageIds` accepts an array; the production handler also accepts a bare string for renderer-compat but the spec models the array shape only. `read` defaults to `true` when omitted. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** |  | [optional] 
**MessageIds** | **List&lt;string&gt;** |  | 
**Read** | **bool** |  | [optional] [default to true]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

