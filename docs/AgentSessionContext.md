# Spatio.Sdk.Model.AgentSessionContext
Identity bundle returned to the agent at SessionStart. One round-trip provides user + current org/workspace + connected accounts so the agent doesn't fish on its first turn. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**User** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**CurrentOrganization** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**CurrentWorkspace** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**ConnectedAccounts** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

