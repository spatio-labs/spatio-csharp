# Spatio.Sdk.Model.Task
A to-do / reminder / issue. Tasks belong to one connected account (`accountId` + `provider`). Native tasks store in Spatio's DB; external providers (Linear, GitHub Issues, Todoist, etc.) round-trip through Spatio. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Provider** | **string** | Registered provider id (e.g. &#x60;native-tasks&#x60;, &#x60;linear&#x60;). | [optional] 
**AccountId** | **string** |  | [optional] 
**OwnerUserId** | **string** |  | [optional] 
**Title** | **string** |  | 
**Description** | **string** |  | [optional] 
**Status** | **string** | Free-form status string. Canonical values across most providers: &#x60;todo&#x60;, &#x60;in_progress&#x60;, &#x60;in_review&#x60;, &#x60;backlog&#x60;, &#x60;done&#x60;. The platform falls back to &#x60;done&#x60; when &#x60;completed&#x60; is true and &#x60;status&#x60; is empty, else &#x60;todo&#x60;.  | [optional] 
**Completed** | **bool** |  | 
**DueDate** | **DateTime?** |  | [optional] 
**Priority** | **string** | Priority bucket. Canonical values (mapped from a 0–4 integer): &#x60;none&#x60;, &#x60;low&#x60;, &#x60;medium&#x60;, &#x60;high&#x60;, &#x60;urgent&#x60;.  | 
**Labels** | **List&lt;string&gt;** |  | [optional] 
**Tags** | **List&lt;string&gt;** |  | [optional] 
**AssigneeId** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**CompletedAt** | **DateTime?** |  | [optional] 
**ParentTaskId** | **string** | Parent task id when this is a subtask. | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Provider-specific extras. | [optional] 
**Type** | **string** | Discriminator. Canonical values: &#x60;todo&#x60;, &#x60;reminder&#x60;, &#x60;issue&#x60;. Empty defaults to &#x60;todo&#x60;.  | [optional] 
**SourcePlatform** | **string** | When this task was auto-generated from another artifact (e.g. a calendar event reminder), the platform id of that artifact.  | [optional] 
**SourceId** | **string** | Source artifact id paired with &#x60;sourcePlatform&#x60;. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

