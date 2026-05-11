# Spatio.Sdk.Model.CreateSlideRequest
`presentationId` in the body is allowed but redundant when posting to `/v1/slides/{id}/slides` — the path id wins. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PresentationId** | **string** |  | [optional] 
**Title** | **string** |  | [optional] 
**Notes** | **string** |  | [optional] 
**Layout** | **string** |  | [optional] 
**BackgroundColor** | **string** |  | [optional] 
**BackgroundImageUrl** | **string** |  | [optional] 
**TextColor** | **string** |  | [optional] 
**Transition** | **string** |  | [optional] 
**Position** | **int** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

