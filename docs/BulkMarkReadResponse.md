# Spatio.Sdk.Model.BulkMarkReadResponse
Partial-success envelope for `bulkMarkEmailsRead`. `updated` is a count (not an array — distinct from archive/delete which return the actual id list). The failed-row shape uses `id` (also distinct — renderer-compat legacy). 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Updated** | **int** | Number of messages successfully marked. | 
**Failed** | [**List&lt;BulkMarkReadResponseFailedInner&gt;**](BulkMarkReadResponseFailedInner.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

