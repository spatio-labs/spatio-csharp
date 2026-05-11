# Spatio.Sdk.Model.SearchFilesResponse
In-memory substring search across the caller's files. Provider filtering isn't standardized across providers, so the platform lists up to ~500 files and filters locally — `total` is the pre-truncation count, not the global count. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Files** | [**List&lt;SpatioFile&gt;**](SpatioFile.md) |  | [optional] 
**Total** | **int** |  | 
**HasMore** | **bool** |  | 
**Query** | **string** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

