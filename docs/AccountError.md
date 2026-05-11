# Spatio.Sdk.Model.AccountError
Per-account failure attached to `AccountStatus.error` inside a fan-out `Envelope`. `code` is machine-readable and stable across releases for the canonical values (`auth_expired`, `rate_limited`, `provider_5xx`, `timeout`); `unknown` is a fallback and should not be relied on. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Code** | **string** |  | 
**Message** | **string** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

