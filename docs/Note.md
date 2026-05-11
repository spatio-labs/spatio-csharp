# Spatio.Sdk.Model.Note
A markdown note. Notes belong to exactly one connected account (`accountId` + `provider`). The native provider stores notes in the Spatio database; external providers (Notion, Google Keep, etc.) store them upstream and round-trip through Spatio. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Stable provider id for the note. | 
**Provider** | **string** | Registered provider id (e.g. &#x60;native-notes&#x60;). | [optional] 
**AccountId** | **string** | Connected-account row this note belongs to. | [optional] 
**OwnerUserId** | **string** | User id of the note&#39;s owner. Surfaced so the renderer can show \&quot;Shared with you\&quot; when &#x60;ownerUserId&#x60; differs from the viewer&#39;s id. Empty for non-native providers.  | [optional] 
**Title** | **string** |  | 
**Content** | **string** | Markdown body. The block tree at &#x60;/v1/notes/{id}/blocks&#x60; is the canonical structured representation; &#x60;content&#x60; is a flattened markdown view kept for clients that don&#39;t render blocks.  | 
**Icon** | **string** | Emoji or short string used as the note&#39;s icon. | [optional] 
**CoverImage** | **string** | URL of the note&#39;s cover image. | [optional] 
**ParentId** | **string** | Parent note id when notes are nested. | [optional] 
**Properties** | **Dictionary&lt;string, Object&gt;** | Free-form provider-specific properties (tags, etc.). | [optional] 
**Archived** | **bool** |  | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**LastEditedBy** | **string** | User id of the most recent editor. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

