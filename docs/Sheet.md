# Spatio.Sdk.Model.Sheet
A spreadsheet. Sheets belong to exactly one connected account (`accountId` + `provider`). The native provider stores sheets in the Spatio database; external providers (Google Sheets, Excel Online, etc.) round-trip through Spatio.  `data` is a free-form bag for provider-specific blobs (cell matrices, formulas, formatting). Clients that walk rows / cells should use the dedicated row + cell endpoints; `data` is only meaningful when round-tripping with an external provider that embeds its native format here. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Provider** | **string** | Registered provider id (e.g. &#x60;native-sheets&#x60;). | [optional] 
**AccountId** | **string** | Connected-account row this sheet belongs to. | [optional] 
**OwnerUserId** | **string** | User id of the sheet owner; non-native providers leave empty. | [optional] 
**Name** | **string** |  | 
**Description** | **string** |  | [optional] 
**Data** | **Dictionary&lt;string, Object&gt;** | Free-form provider blob. Treat as opaque. | [optional] 
**RowCount** | **int** |  | 
**ColumnCount** | **int** |  | 
**SheetCount** | **int** | Tab count when the file contains multiple sheets. | 
**IsPublic** | **bool** |  | 
**IsReadOnly** | **bool** |  | 
**FileSize** | **int?** |  | [optional] 
**LastAccessedAt** | **DateTime?** |  | [optional] 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

