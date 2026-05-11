# Spatio.Sdk.Model.AccountListResponse
`GET /v1/accounts` returns `{accounts_by_platform, total_accounts}` on production today. Schema kept open until the consumers migrate to a flat `accounts` array. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountsByPlatform** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**TotalAccounts** | **int** |  | [optional] 
**Accounts** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

