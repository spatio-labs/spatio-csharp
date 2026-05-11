# Spatio.Sdk.Model.BlockContent
Type-specific payload for a block. Fields populated depend on `Block.type`. All fields are optional at the schema level; the runtime enforces the per-type contract.  Note: this object uses snake_case keys to match the JSON the Go `providers.BlockContent` struct emits and accepts. Other parts of the SpatioAPI use camelCase; blocks are the exception because the block model is shared with external Notion-like providers whose canonical wire format is snake_case. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**RichText** | [**List&lt;RichTextObject&gt;**](RichTextObject.md) |  | [optional] 
**Language** | **string** | Programming language for &#x60;code&#x60; blocks. | [optional] 
**Checked** | **bool** | Toggle state for &#x60;to_do&#x60; blocks. | [optional] 
**Icon** | **string** | Emoji or short string for &#x60;callout&#x60; blocks. | [optional] 
**Color** | **string** | Theme color for &#x60;callout&#x60; blocks. | [optional] 
**Url** | **string** | Source URL for &#x60;image&#x60;, &#x60;video&#x60;, &#x60;file&#x60; blocks. | [optional] 
**Caption** | **string** | Visible caption for media blocks. | [optional] 
**AltText** | **string** | Screen-reader description for media blocks. Distinct from &#x60;caption&#x60; (visible to readers) — required for accessible notes when the image conveys meaning.  | [optional] 
**EmbedUrl** | **string** | Source URL for &#x60;embed&#x60; blocks. | [optional] 
**Cells** | **List&lt;List&lt;RichTextObject&gt;&gt;** | 2D rich-text grid for &#x60;table&#x60; and &#x60;table_row&#x60; blocks. | [optional] 
**Expression** | **string** | TeX/MathJax expression for &#x60;equation&#x60; blocks. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

