# Spatio.Sdk.Model.Presentation
A slide deck. Presentations belong to one connected account (`accountId` + `provider`). Native deck storage lives in Spatio's DB; external providers (Google Slides, etc.) round-trip. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Provider** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**OwnerUserId** | **string** |  | [optional] 
**Title** | **string** |  | 
**Description** | **string** |  | [optional] 
**Theme** | **string** | Free-form theme id; provider-specific. | [optional] 
**ThumbnailUrl** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**LastViewedAt** | **DateTime?** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

