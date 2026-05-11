# Spatio.Sdk.Model.ExportPDFRequest
Optional body for `POST /v1/slides/{id}/export/pdf`. Renderer posts pre-rasterized PNGs for slides that contain Fabric.js elements (the sidecar can't run Fabric server-side); slides without an entry are rendered from their `layout` + theme. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**RasterizedSlides** | [**List&lt;ExportPDFRequestRasterizedSlidesInner&gt;**](ExportPDFRequestRasterizedSlidesInner.md) |  | [optional] 
**Theme** | **Dictionary&lt;string, Object&gt;** | Optional palette override. Schemaless — the export sidecar accepts a free-form palette object. Treat as opaque.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

