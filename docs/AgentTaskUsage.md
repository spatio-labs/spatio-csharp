# Spatio.Sdk.Model.AgentTaskUsage
Free-trial agent-task gate. `allowed` is the only field clients must check before issuing a turn. Paid users get `paid: true, allowed: true` with the count fields null. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Allowed** | **bool** |  | 
**TaskCount** | **int?** |  | [optional] 
**DailyLimit** | **int?** |  | [optional] 
**TrialEndsAt** | **DateTime?** |  | [optional] 
**Paid** | **bool** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

