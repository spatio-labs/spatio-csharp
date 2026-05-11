# Spatio.Sdk.Model.Slide

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Provider** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**PresentationId** | **string** |  | 
**Title** | **string** |  | 
**Notes** | **string** | Speaker notes. | [optional] 
**Layout** | **string** | Free-form layout id. Provider-specific (&#x60;title&#x60;, &#x60;two-column&#x60;, &#x60;image-left&#x60;, custom). Not enumerated to avoid forcing a breaking change every time a provider adds one.  | [optional] 
**BackgroundColor** | **string** |  | [optional] 
**BackgroundImageUrl** | **string** |  | [optional] 
**TextColor** | **string** |  | [optional] 
**Transition** | **string** | Free-form transition id. | [optional] 
**Position** | **int** | Zero-based position within the presentation. | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

