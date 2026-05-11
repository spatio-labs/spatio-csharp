# Spatio.Sdk.Model.BlockListResponse
Single-account list response for `GET /v1/notes/{id}/blocks`. Unlike `GET /v1/notes`, block listing always targets one account so it does not fan out — `total` is the count for the current page slice. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Blocks** | [**List&lt;Block&gt;**](Block.md) |  | 
**Total** | **int** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

