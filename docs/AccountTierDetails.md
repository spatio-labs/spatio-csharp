# Spatio.Sdk.Model.AccountTierDetails
Per-tier capability + quota envelope. Numeric quotas use 0/-1 idioms; treat large negatives as \"unlimited.\"

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Tier** | **string** |  | 
**DailyApiCalls** | **int** |  | [optional] 
**MaxConnectedAccounts** | **int** |  | [optional] 
**MaxEmailSendsPerDay** | **int** |  | [optional] 
**MaxNotes** | **int** |  | [optional] 
**MaxSheets** | **int** |  | [optional] 
**MaxSlides** | **int** |  | [optional] 
**MaxFiles** | **int** |  | [optional] 
**MaxTasks** | **int** |  | [optional] 
**MaxTeamMembers** | **int** |  | [optional] 
**MaxWorkspaces** | **int** |  | [optional] 
**StorageGb** | **int** |  | [optional] 
**HasAutomations** | **bool** |  | [optional] 
**HasAdvancedAutomations** | **bool** |  | [optional] 
**HasFullApiAccess** | **bool** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

