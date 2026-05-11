# Spatio.Sdk.Model.SpatioEvent
A calendar event. Calendar uses snake_case JSON keys (different from Notes/Sheets/Slides/Tasks/Mail which use camelCase) — the surface predates the cross-platform convention. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Title** | **string** |  | 
**Description** | **string** |  | [optional] 
**StartTime** | **DateTime** |  | 
**EndTime** | **DateTime** |  | 
**AllDay** | **bool** |  | 
**Location** | **string** |  | [optional] 
**LocationDetails** | **Dictionary&lt;string, string&gt;** | Free-form key/value (lat, lng, room, etc.). | [optional] 
**Organizer** | **string** | Organizer email. | [optional] 
**Attendees** | [**List&lt;Attendee&gt;**](Attendee.md) |  | [optional] 
**RecurrenceRule** | **string** | RFC 5545 RRULE. | [optional] 
**RecurrenceId** | **string** | Set on instances of a recurring series. | [optional] 
**OriginalStart** | **DateTime** | Original start of a moved recurring instance. | [optional] 
**Status** | **string** | Provider-mapped event status. Free-form string — common values are &#x60;confirmed&#x60;, &#x60;tentative&#x60;, &#x60;cancelled&#x60;, &#x60;needs_action&#x60;, and the empty string when the provider doesn&#39;t populate it. Not enumerated strictly because providers add custom values and the platform passes them through verbatim.  | 
**Visibility** | **string** | Free-form visibility string. Common values: &#x60;public&#x60;, &#x60;private&#x60;, &#x60;confidential&#x60;, plus empty when unset.  | 
**Busy** | **bool** | Whether this event marks the time as busy or free. | 
**Reminders** | [**List&lt;Reminder&gt;**](Reminder.md) |  | [optional] 
**TravelTimeMinutes** | **int?** | Apple Calendar&#39;s local-only travel buffer. Stored on the cached row but not synced to providers that don&#39;t model it.  | [optional] 
**Categories** | **List&lt;string&gt;** |  | [optional] 
**Color** | **string** |  | [optional] 
**UserId** | **string** |  | [optional] 
**AccountId** | **string** |  | 
**Provider** | **string** | Standardized provider id (e.g. &#x60;google-calendar&#x60;, &#x60;native-calendar&#x60;). Mirrors &#x60;provider_id&#x60; — both are populated on writes; clients should prefer &#x60;provider&#x60;.  | [optional] 
**ProviderId** | **string** | Legacy alias of &#x60;provider&#x60;. | 
**ProviderData** | **Dictionary&lt;string, Object&gt;** | Provider-specific extras. | [optional] 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**DeletedAt** | **DateTime?** |  | [optional] 
**SyncedAt** | **DateTime** |  | [optional] 
**ConferenceData** | [**ConferenceData**](ConferenceData.md) |  | [optional] 
**Attachments** | [**List&lt;Attachment&gt;**](Attachment.md) |  | [optional] 
**Url** | **string** |  | [optional] 
**Etag** | **string** |  | [optional] 
**Sequence** | **int** |  | [optional] 
**CustomData** | **Dictionary&lt;string, string&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

