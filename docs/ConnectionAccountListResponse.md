# Spatio.Sdk.Model.ConnectionAccountListResponse
`GET /v1/connections/user` returns `{connections, user_id}` (the per-provider connected-account list). Schema kept open pending a normalize-to-`accounts` migration. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Connections** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** |  | [optional] 
**UserId** | **string** |  | [optional] 
**Accounts** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

