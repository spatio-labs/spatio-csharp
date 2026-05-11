# Spatio.Sdk.Model.ConferenceData
Video/phone conference details. `type` is canonical (`spatio`, `meet`, `zoom`, `teams`); other provider-specific values are accepted as opaque strings. The Spatio invite email pipeline only fires for native events or events with `type: spatio`. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** |  | 
**Uri** | **string** |  | 
**MeetingId** | **string** |  | [optional] 
**Passcode** | **string** |  | [optional] 
**AccessCode** | **string** |  | [optional] 
**DialIn** | **List&lt;string&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

