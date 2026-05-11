# Spatio.Sdk.Model.FilesAndFoldersResponse
Aggregated `{files, folders, accounts}` envelope used by the renderer's file-browser. Calls `ListFiles` and `ListFolders` in parallel and merges the results — saves a round-trip when the UI shows both side-by-side. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Files** | [**List&lt;SpatioFile&gt;**](SpatioFile.md) |  | [optional] 
**Folders** | [**List&lt;Folder&gt;**](Folder.md) |  | [optional] 
**Accounts** | [**List&lt;AccountStatus&gt;**](AccountStatus.md) |  | [optional] 
**Total** | **int** |  | 
**HasMore** | **bool** |  | 
**NextOffset** | **int** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

