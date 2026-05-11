# Spatio.Sdk.Model.ExtractTextResult
Extracted text + structural metadata from a PDF (or other extraction-supported file type). `pages` is provider-shaped — treat as an opaque per-page object array. Endpoint returns `422` with `code: extraction_unsupported` when the underlying file isn't extractable. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Text** | **string** |  | 
**PageCount** | **int** |  | 
**Pages** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** |  | [optional] 
**Truncated** | **bool** | &#x60;true&#x60; when &#x60;maxChars&#x60; was hit before the end. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

