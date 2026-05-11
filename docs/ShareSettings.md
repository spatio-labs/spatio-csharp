# Spatio.Sdk.Model.ShareSettings
Public share configuration for a note. Owner-only mutation; unauthenticated readers consume `GET /public/notes/{token}` instead. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**IsPublic** | **bool** |  | 
**HasPassword** | **bool** |  | 
**ShareToken** | **string** | Opaque token embedded in the public URL. Empty when &#x60;isPublic&#x60; is false.  | [optional] 
**ShareUrl** | **string** | Fully-qualified public viewer URL. Computed server-side from &#x60;PUBLIC_VIEWER_BASE&#x60; (defaults to &#x60;https://spatio.app&#x60;) and the share token. Empty when the note is private.  | [optional] 
**PasswordSetAt** | **DateTime** | When the current password was set, if any. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

