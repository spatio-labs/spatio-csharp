# Spatio.Sdk.Model.ChunkedFileManifest
Block-level manifest for a chunked-uploaded file. Returned by `GET /v1/files/{id}/manifest`. Only meaningful for files uploaded via the chunked path; legacy uploads return `404`. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ManifestId** | **string** |  | 
**FileId** | **string** |  | 
**FileName** | **string** |  | 
**VarVersion** | **int** |  | 
**TotalSize** | **long** |  | 
**BlockCount** | **int** |  | 
**ChunkingAlgorithm** | **string** |  | [optional] 
**FileChecksum** | **string** |  | [optional] 
**Blocks** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

