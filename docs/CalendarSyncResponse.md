# Spatio.Sdk.Model.CalendarSyncResponse
Returned by `POST /v1/calendar/sync`. Status code is `202` by default (sync jobs queued); `200` when called with `?wait=true` and all jobs finish within the 10-second polling budget. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Enqueued** | **int** |  | 
**Jobs** | **List&lt;string&gt;** |  | 
**Waited** | **bool** |  | [optional] 
**TimedOut** | **bool** |  | [optional] 
**Errors** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

