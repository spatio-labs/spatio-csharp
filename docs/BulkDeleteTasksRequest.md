# Spatio.Sdk.Model.BulkDeleteTasksRequest
Either populate `taskIds` (with optional parallel `accountIds`) for multi-task delete, or `taskId` (with optional `accountId`) for the single-task fallback. `taskIds` wins when both are set. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**TaskIds** | **List&lt;string&gt;** |  | [optional] 
**AccountIds** | **List&lt;string&gt;** | Parallel slice with taskIds — accountIds[i] targets taskIds[i]. | [optional] 
**TaskId** | **string** | Singular fallback when only deleting one task. | [optional] 
**AccountId** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

