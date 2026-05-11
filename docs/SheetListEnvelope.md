# Spatio.Sdk.Model.SheetListEnvelope
Fan-out response for `GET /v1/sheets`. `items` aggregates sheets across every connected account; `accounts` carries one row per contributing connection — including failures. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Items** | [**List&lt;Sheet&gt;**](Sheet.md) |  | 
**Accounts** | [**List&lt;AccountStatus&gt;**](AccountStatus.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

