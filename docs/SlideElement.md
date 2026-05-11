# Spatio.Sdk.Model.SlideElement
One canvas object on a slide — text box, shape, image, etc. `content` is renderer-specific JSON (e.g. fabric.js properties: text, fill, fontSize, src). Identified by a stable `id` so MCP / agent operations stay idempotent across retries. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**SlideId** | **string** |  | 
**ElementType** | **string** | Free-form type id (&#x60;text&#x60;, &#x60;image&#x60;, &#x60;shape&#x60;, etc.). | 
**Content** | **Dictionary&lt;string, Object&gt;** |  | 
**X** | **double** |  | 
**Y** | **double** |  | 
**Width** | **double** |  | 
**Height** | **double** |  | 
**Rotation** | **double** | Degrees. | 
**ZIndex** | **int** |  | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

