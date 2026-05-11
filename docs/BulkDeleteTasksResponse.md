# Spatio.Sdk.Model.BulkDeleteTasksResponse
Partial-success envelope. `success` is `true` only when zero failures; `affectedCount` is the deleted count; `taskIds` lists the ids that succeeded; `failed` lists per-id errors. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Success** | **bool** |  | 
**AffectedCount** | **int** |  | 
**TaskIds** | **List&lt;string&gt;** |  | 
**Failed** | [**List&lt;BulkDeleteTasksResponseFailedInner&gt;**](BulkDeleteTasksResponseFailedInner.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

