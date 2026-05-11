# Spatio.Sdk.Model.ConsumeAgentTaskResponse
Atomic check+increment. Returns the updated counter on success; returns 402 on `trial_expired` and 429 on `daily_limit_exceeded` (the body in error cases is the `ApiError` envelope). 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Allowed** | **bool** |  | 
**TaskCount** | **int?** |  | [optional] 
**DailyLimit** | **int?** |  | [optional] 
**TrialEndsAt** | **DateTime?** |  | [optional] 
**Paid** | **bool** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

