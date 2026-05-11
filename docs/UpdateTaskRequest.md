# Spatio.Sdk.Model.UpdateTaskRequest
Partial update — every field is optional. `dueDate` and `parentTaskId` are nullable: send `null` to clear, omit to leave untouched, send a value to set. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Title** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**Status** | **string** |  | [optional] 
**DueDate** | **DateTime?** |  | [optional] 
**Priority** | **string** |  | [optional] 
**Labels** | **List&lt;string&gt;** |  | [optional] 
**Tags** | **List&lt;string&gt;** |  | [optional] 
**AssigneeId** | **string** |  | [optional] 
**ParentTaskId** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

