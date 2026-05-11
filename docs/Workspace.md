# Spatio.Sdk.Model.Workspace
A workspace within an organization. Returned in list responses (`GET /v1/workspaces`, `GET /v1/organizations/{id}/workspaces`) and the single-get response (`GET /v1/workspaces/{id}`, wrapped in `{workspace: ...}`).  `settings` shape varies by endpoint — sometimes a JSON object, sometimes a JSON-encoded string. Treat as opaque. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Name** | **string** |  | 
**Slug** | **string** |  | 
**Description** | **string** |  | [optional] 
**LogoUrl** | **string** |  | [optional] 
**OrganizationId** | **string** |  | [optional] 
**Organization** | [**WorkspaceOrganization**](WorkspaceOrganization.md) |  | [optional] 
**Role** | **string** | The caller&#39;s role in this workspace (&#x60;owner&#x60;, &#x60;admin&#x60;, &#x60;member&#x60;, &#x60;guest&#x60;). | [optional] 
**Settings** | **Object** | Per-workspace settings. Currently emitted as either an object (&#x60;{language, timezone, ...}&#x60;) on &#x60;GET /v1/workspaces/{id}&#x60; or a JSON-encoded string on &#x60;GET /v1/organizations/{id}/workspaces&#x60;. Treat as opaque and parse defensively.  | [optional] 
**IsDefault** | **bool** |  | [optional] 
**MemberCount** | **int** |  | [optional] 
**BillingTier** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**UpdatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

