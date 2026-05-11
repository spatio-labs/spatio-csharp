# Spatio.Sdk.Model.AccountPlan
Subscription summary. `tier` is the canonical billing tier (uppercased: `FREE`, `PRO`, `MAX`, `ENTERPRISE`); `display_name` is the lowercase user-facing label. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Tier** | **string** |  | 
**DisplayName** | **string** |  | 
**SubscriptionStatus** | **string** | Stripe subscription state: &#x60;ACTIVE&#x60;, &#x60;TRIALING&#x60;, &#x60;PAST_DUE&#x60;, &#x60;CANCELED&#x60;, etc. | 
**TrialEndsAt** | **DateTime?** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

