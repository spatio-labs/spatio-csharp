# Spatio.Sdk.Model.ListEventsData
Shape of `data` when returned by `listEvents`. Wrapped inside a CalendarOperationResult — clients should access this as `result.data` after checking `result.success`. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Events** | [**List&lt;SpatioEvent&gt;**](SpatioEvent.md) | &#x60;null&#x60; when there are no results (Go nil-slice serialization).  | [optional] 
**NextPageToken** | **string** |  | [optional] 
**TotalResults** | **int** |  | [optional] 
**UpdatedAt** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

