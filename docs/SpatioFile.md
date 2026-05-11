# Spatio.Sdk.Model.SpatioFile
A user file. Files belong to one connected file provider account (`accountId` + `provider`); native storage uses Spatio's block-store, external providers (Google Drive, Dropbox, etc.) round-trip through Spatio.  Schema name is `SpatioFile` (not `File`) to avoid the `java.io.File` collision that breaks the Kotlin SDK generator when the schema is named `File`. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Provider** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**Name** | **string** |  | 
**Size** | **long** | Bytes. | 
**MimeType** | **string** |  | 
**FolderId** | **string** |  | [optional] 
**StorageType** | **string** | Backing storage class — &#x60;r2&#x60;, &#x60;gdrive&#x60;, &#x60;dropbox&#x60;, etc. Provider-specific; treat as opaque.  | 
**DownloadUrl** | **string** | Pre-signed download URL when one is cached on the row. Use &#x60;GET /v1/files/{id}/download&#x60; for a guaranteed-fresh URL — this field can lag past expiry.  | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

