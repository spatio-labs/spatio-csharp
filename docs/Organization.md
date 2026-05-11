# Spatio.Sdk.Model.Organization
Organization summary used in list responses (`GET /v1/organizations`, `GET /v1/organizations/{id}/workspaces`). Returned with camelCase field names.  NB: The single-org GET `/v1/organizations/{id}` returns a *different shape* (`OrganizationDetailLegacy`, PascalCase keys) today — see that schema for the wire-level reality. This is a known inconsistency the platform-service is expected to converge on the camelCase shape in a future cleanup. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Name** | **string** |  | 
**Slug** | **string** |  | 
**Description** | **string** |  | [optional] 
**LogoUrl** | **string** |  | [optional] 
**Role** | **string** | The caller&#39;s role in this org (&#x60;owner&#x60;, &#x60;admin&#x60;, &#x60;billing_admin&#x60;, &#x60;member&#x60;). | 
**MemberCount** | **int** |  | [optional] 
**WorkspaceCount** | **int** |  | [optional] 
**Workspaces** | [**List&lt;OrganizationWorkspacesInner&gt;**](OrganizationWorkspacesInner.md) | Compact workspace summaries embedded in the org-list response. | [optional] 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

