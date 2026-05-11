# Spatio.Sdk.Model.OrganizationInvitation

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**OrganizationId** | **string** |  | [optional] 
**Email** | **string** |  | 
**Role** | **string** |  | 
**Token** | **string** | Opaque invitation token (omitted on list responses). | [optional] 
**ExpiresAt** | **DateTime?** |  | [optional] 
**CreatedAt** | **DateTime** |  | 
**AcceptedAt** | **DateTime?** |  | [optional] 
**RevokedAt** | **DateTime?** |  | [optional] 
**InvitedBy** | [**OrganizationMemberInvitedBy**](OrganizationMemberInvitedBy.md) |  | [optional] 
**Status** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

