# Spatio.Sdk.Model.FederatedSearch200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Items** | [**List&lt;FederatedSearch200ResponseItemsInner&gt;**](FederatedSearch200ResponseItemsInner.md) |  | 
**NextPageTokens** | **Dictionary&lt;string, string&gt;** |  | [optional] 
**PerPlatform** | [**Dictionary&lt;string, FederatedSearch200ResponsePerPlatformValue&gt;**](FederatedSearch200ResponsePerPlatformValue.md) |  | 
**Errors** | **Dictionary&lt;string, string&gt;** | Per-platform errors. Other platforms still return results. | [optional] 
**TotalReturned** | **int** |  | 
**Took** | **string** | Aggregate wall-clock time for the fan-out, e.g. \&quot;120ms\&quot;. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

