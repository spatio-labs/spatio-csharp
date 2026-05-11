# Spatio.Sdk.Model.CalendarOperationResult
Generic platform-operation envelope used by Calendar list/create/ update/delete responses. `data` is operation-specific:   - listEvents: `ListEventsData`   - createEvent / updateEvent: `Event`   - deleteEvent: empty / metadata-only 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Success** | **bool** |  | 
**Data** | **Object** | Operation-specific payload. See the operation&#39;s response description for the concrete shape.  | [optional] 
**Errors** | [**List&lt;CalendarAccountError&gt;**](CalendarAccountError.md) |  | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

