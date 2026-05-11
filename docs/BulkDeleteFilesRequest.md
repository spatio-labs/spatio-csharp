# Spatio.Sdk.Model.BulkDeleteFilesRequest
Either `fileIds` (with optional parallel `accountIds`) for multi-file delete, or `fileId` (with optional `accountId`) for the single-file fallback. `fileIds` wins when both are set. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**FileIds** | **List&lt;string&gt;** |  | [optional] 
**AccountIds** | **List&lt;string&gt;** | Parallel slice with fileIds — accountIds[i] targets fileIds[i]. | [optional] 
**FileId** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

