# Spatio.Sdk.Model.TokenResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccessToken** | **string** | Opaque bearer token. Format &#x60;tok_&lt;32 random base64url&gt;&#x60;. | 
**TokenType** | **string** |  | 
**ExpiresIn** | **int** | Seconds until access_token expires. | 
**RefreshToken** | **string** |  | [optional] 
**Scope** | **string** |  | [optional] 
**IdToken** | **string** | Only present when &#x60;openid&#x60; scope was granted. RS256-signed JWT — verify against the JWKS. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

