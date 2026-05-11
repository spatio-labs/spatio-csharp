# Spatio.Sdk.Model.ExportPDFR2Response
Response shape when the export was uploaded to R2 (`?storage=r2`). The streaming case (`?storage=stream`, default) returns a binary `application/pdf` body and is not modeled as a JSON schema. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Storage** | **string** |  | 
**Url** | **string** | 24-hour signed URL. | 
**ExpiresAt** | **DateTime** |  | 
**Size** | **int** | PDF size in bytes. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

