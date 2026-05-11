# Spatio.Sdk.Model.Comment
Threaded comment on a note. Top-level comments have `parentCommentId: null`; replies set it to the parent comment's id. `blockId` anchors the comment to a specific block; comments without a `blockId` are note-level (\"general\") comments. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**NoteId** | **string** |  | 
**ParentCommentId** | **string** |  | [optional] 
**BlockId** | **string** |  | [optional] 
**Body** | **string** |  | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**Author** | [**CommentAuthor**](CommentAuthor.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

