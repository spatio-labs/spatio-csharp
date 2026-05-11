# Spatio.Sdk.Model.EnableShareRequest
Body for `POST /v1/notes/{id}/share`. With `setPassword: false`, only the public flag is flipped — any existing password is preserved. With `setPassword: true`, the supplied `password` is applied (an empty string clears it). 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**SetPassword** | **bool** |  | [optional] 
**Password** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

