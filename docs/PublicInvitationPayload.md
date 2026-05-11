# Spatio.Sdk.Model.PublicInvitationPayload
Returned by `GET /invitations/{token}` (unauthenticated). Lets the renderer show invitation details (workspace name, inviter, role) before the user signs in. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Kind** | **string** |  | 
**Id** | **string** |  | 
**WorkspaceId** | **string** |  | [optional] 
**OrganizationId** | **string** |  | [optional] 
**Email** | **string** |  | 
**Role** | **string** |  | 
**Status** | **string** |  | 
**ExpiresAt** | **DateTime?** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**Workspace** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**Organization** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**InvitedBy** | **Dictionary&lt;string, Object&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

