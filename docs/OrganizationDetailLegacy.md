# Spatio.Sdk.Model.OrganizationDetailLegacy
Single-organization GET response. **PascalCase keys** — inconsistent with the rest of the API (anonymous-struct json-marshal in handler with no field tags). Documented as-is; a future cleanup pass will move this to camelCase via a versioned migration. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ID** | **string** |  | 
**Name** | **string** |  | 
**Slug** | **string** |  | 
**Description** | **string** |  | [optional] 
**LogoURL** | **string** |  | [optional] 
**Settings** | **string** | JSON-encoded settings string. Parse client-side. | [optional] 
**SubscriptionTier** | **string** |  | 
**DeploymentType** | **string** |  | 
**SubscriptionStatus** | **string** |  | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

