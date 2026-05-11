# Spatio.Sdk.Model.BulkArchiveResponse
Partial-success envelope for `bulkArchiveEmails`.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Success** | **bool** | &#x60;true&#x60; only when zero rows in &#x60;failed&#x60;. | 
**Archived** | **List&lt;string&gt;** |  | 
**Failed** | [**List&lt;BulkArchiveResponseFailedInner&gt;**](BulkArchiveResponseFailedInner.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

