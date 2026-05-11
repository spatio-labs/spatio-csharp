# Spatio.Sdk.Api.OrganizationsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AcceptOrganizationInvitation**](OrganizationsApi.md#acceptorganizationinvitation) | **POST** /v1/organizations/{org}/accept-invitation | Accept an invitation to this organization. |
| [**AddOrganizationMember**](OrganizationsApi.md#addorganizationmember) | **POST** /v1/organizations/{org}/members | Add a member directly (skips invitation flow). |
| [**CreateOrganization**](OrganizationsApi.md#createorganization) | **POST** /v1/organizations | Create an organization. |
| [**CreateOrganizationConcept**](OrganizationsApi.md#createorganizationconcept) | **POST** /v1/organizations/{org}/concepts | Create an org-brain concept (admin+ only). |
| [**CreateOrganizationCustomRole**](OrganizationsApi.md#createorganizationcustomrole) | **POST** /v1/organizations/{org}/roles | Create a custom role (admin+ only). |
| [**CreateOrganizationInvitation**](OrganizationsApi.md#createorganizationinvitation) | **POST** /v1/organizations/{org}/invitations | Invite a user to the organization. |
| [**CreateOrganizationWorkspace**](OrganizationsApi.md#createorganizationworkspace) | **POST** /v1/organizations/{org}/workspaces | Create a workspace inside an organization. |
| [**DeleteOrganization**](OrganizationsApi.md#deleteorganization) | **DELETE** /v1/organizations/{org} | Delete an organization. |
| [**DeleteOrganizationConcept**](OrganizationsApi.md#deleteorganizationconcept) | **DELETE** /v1/organizations/{org}/concepts/{slug} | Delete a concept (admin+ only). |
| [**DeleteOrganizationCustomRole**](OrganizationsApi.md#deleteorganizationcustomrole) | **DELETE** /v1/organizations/{org}/roles/{roleId} | Delete a custom role (admin+ only). |
| [**DeleteOrganizationLogo**](OrganizationsApi.md#deleteorganizationlogo) | **DELETE** /v1/organizations/{org}/logo | Delete the organization logo. |
| [**GetOrganization**](OrganizationsApi.md#getorganization) | **GET** /v1/organizations/{org} | Fetch a single organization. |
| [**GetOrganizationConcept**](OrganizationsApi.md#getorganizationconcept) | **GET** /v1/organizations/{org}/concepts/{slug} | Fetch a concept. |
| [**ListMyOrganizations**](OrganizationsApi.md#listmyorganizations) | **GET** /v1/organizations | List the caller&#39;s organizations. |
| [**ListOrganizationAuditLog**](OrganizationsApi.md#listorganizationauditlog) | **GET** /v1/organizations/{org}/audit-log | Read the organization audit log (admin / billing-admin only). |
| [**ListOrganizationConcepts**](OrganizationsApi.md#listorganizationconcepts) | **GET** /v1/organizations/{org}/concepts | List org-brain concepts (curated knowledge surfaced to agents). |
| [**ListOrganizationCustomRoles**](OrganizationsApi.md#listorganizationcustomroles) | **GET** /v1/organizations/{org}/roles | List custom roles defined on the organization. |
| [**ListOrganizationInvitations**](OrganizationsApi.md#listorganizationinvitations) | **GET** /v1/organizations/{org}/invitations | List pending invitations for an organization. |
| [**ListOrganizationMembers**](OrganizationsApi.md#listorganizationmembers) | **GET** /v1/organizations/{org}/members | List members of an organization. |
| [**ListOrganizationWorkspaces**](OrganizationsApi.md#listorganizationworkspaces) | **GET** /v1/organizations/{org}/workspaces | List workspaces in an organization. |
| [**RemoveOrganizationMember**](OrganizationsApi.md#removeorganizationmember) | **DELETE** /v1/organizations/{org}/members/{memberId} | Remove a member from the organization. |
| [**ResendOrganizationInvitation**](OrganizationsApi.md#resendorganizationinvitation) | **POST** /v1/organizations/{org}/invitations/{invitationId}/resend | Revoke and reissue an invitation with a fresh token. |
| [**RevokeOrganizationInvitation**](OrganizationsApi.md#revokeorganizationinvitation) | **DELETE** /v1/organizations/{org}/invitations/{invitationId} | Revoke a pending invitation. |
| [**UpdateOrganization**](OrganizationsApi.md#updateorganization) | **PATCH** /v1/organizations/{org} | Update organization metadata. |
| [**UpdateOrganizationConcept**](OrganizationsApi.md#updateorganizationconcept) | **PATCH** /v1/organizations/{org}/concepts/{slug} | Update a concept (admin+ only). |
| [**UpdateOrganizationCustomRole**](OrganizationsApi.md#updateorganizationcustomrole) | **PATCH** /v1/organizations/{org}/roles/{roleId} | Update a custom role (admin+ only). |
| [**UpdateOrganizationMember**](OrganizationsApi.md#updateorganizationmember) | **PATCH** /v1/organizations/{org}/members/{memberId} | Update a member&#39;s role. |
| [**UploadOrganizationLogo**](OrganizationsApi.md#uploadorganizationlogo) | **POST** /v1/organizations/{org}/logo | Upload (or replace) the organization logo. Multipart. |

<a id="acceptorganizationinvitation"></a>
# **AcceptOrganizationInvitation**
> Dictionary&lt;string, Object&gt; AcceptOrganizationInvitation (string org, AcceptOrganizationInvitationRequest acceptOrganizationInvitationRequest)

Accept an invitation to this organization.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class AcceptOrganizationInvitationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var acceptOrganizationInvitationRequest = new AcceptOrganizationInvitationRequest(); // AcceptOrganizationInvitationRequest | 

            try
            {
                // Accept an invitation to this organization.
                Dictionary<string, Object> result = apiInstance.AcceptOrganizationInvitation(org, acceptOrganizationInvitationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.AcceptOrganizationInvitation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the AcceptOrganizationInvitationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Accept an invitation to this organization.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.AcceptOrganizationInvitationWithHttpInfo(org, acceptOrganizationInvitationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.AcceptOrganizationInvitationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **acceptOrganizationInvitationRequest** | [**AcceptOrganizationInvitationRequest**](AcceptOrganizationInvitationRequest.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invitation accepted. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **410** | Invitation already accepted, revoked, or expired. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="addorganizationmember"></a>
# **AddOrganizationMember**
> Dictionary&lt;string, Object&gt; AddOrganizationMember (string org, AddOrganizationMemberRequest addOrganizationMemberRequest)

Add a member directly (skips invitation flow).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class AddOrganizationMemberExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var addOrganizationMemberRequest = new AddOrganizationMemberRequest(); // AddOrganizationMemberRequest | 

            try
            {
                // Add a member directly (skips invitation flow).
                Dictionary<string, Object> result = apiInstance.AddOrganizationMember(org, addOrganizationMemberRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.AddOrganizationMember: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the AddOrganizationMemberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Add a member directly (skips invitation flow).
    ApiResponse<Dictionary<string, Object>> response = apiInstance.AddOrganizationMemberWithHttpInfo(org, addOrganizationMemberRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.AddOrganizationMemberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **addOrganizationMemberRequest** | [**AddOrganizationMemberRequest**](AddOrganizationMemberRequest.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Member added. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **402** | Seat cap exceeded on free tier. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createorganization"></a>
# **CreateOrganization**
> Dictionary&lt;string, Object&gt; CreateOrganization (CreateOrganizationRequest createOrganizationRequest)

Create an organization.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class CreateOrganizationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var createOrganizationRequest = new CreateOrganizationRequest(); // CreateOrganizationRequest | 

            try
            {
                // Create an organization.
                Dictionary<string, Object> result = apiInstance.CreateOrganization(createOrganizationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.CreateOrganization: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateOrganizationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create an organization.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.CreateOrganizationWithHttpInfo(createOrganizationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.CreateOrganizationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createOrganizationRequest** | [**CreateOrganizationRequest**](CreateOrganizationRequest.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Organization created (with optional default workspace). |  -  |
| **400** | Invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createorganizationconcept"></a>
# **CreateOrganizationConcept**
> Dictionary&lt;string, Object&gt; CreateOrganizationConcept (string org, Dictionary<string, Object> requestBody)

Create an org-brain concept (admin+ only).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class CreateOrganizationConceptExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                // Create an org-brain concept (admin+ only).
                Dictionary<string, Object> result = apiInstance.CreateOrganizationConcept(org, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.CreateOrganizationConcept: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateOrganizationConceptWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create an org-brain concept (admin+ only).
    ApiResponse<Dictionary<string, Object>> response = apiInstance.CreateOrganizationConceptWithHttpInfo(org, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.CreateOrganizationConceptWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **requestBody** | [**Dictionary&lt;string, Object&gt;**](Object.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createorganizationcustomrole"></a>
# **CreateOrganizationCustomRole**
> Dictionary&lt;string, Object&gt; CreateOrganizationCustomRole (string org, Dictionary<string, Object> requestBody)

Create a custom role (admin+ only).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class CreateOrganizationCustomRoleExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                // Create a custom role (admin+ only).
                Dictionary<string, Object> result = apiInstance.CreateOrganizationCustomRole(org, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.CreateOrganizationCustomRole: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateOrganizationCustomRoleWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a custom role (admin+ only).
    ApiResponse<Dictionary<string, Object>> response = apiInstance.CreateOrganizationCustomRoleWithHttpInfo(org, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.CreateOrganizationCustomRoleWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **requestBody** | [**Dictionary&lt;string, Object&gt;**](Object.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createorganizationinvitation"></a>
# **CreateOrganizationInvitation**
> OrganizationInvitation CreateOrganizationInvitation (string org, CreateOrganizationInvitationRequest createOrganizationInvitationRequest)

Invite a user to the organization.

Pending invitations count toward seat cap. Free-tier callers at the cap receive a `402` with billing-upgrade payload; paid-tier auto-scales the Stripe quantity. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class CreateOrganizationInvitationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var createOrganizationInvitationRequest = new CreateOrganizationInvitationRequest(); // CreateOrganizationInvitationRequest | 

            try
            {
                // Invite a user to the organization.
                OrganizationInvitation result = apiInstance.CreateOrganizationInvitation(org, createOrganizationInvitationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.CreateOrganizationInvitation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateOrganizationInvitationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Invite a user to the organization.
    ApiResponse<OrganizationInvitation> response = apiInstance.CreateOrganizationInvitationWithHttpInfo(org, createOrganizationInvitationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.CreateOrganizationInvitationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **createOrganizationInvitationRequest** | [**CreateOrganizationInvitationRequest**](CreateOrganizationInvitationRequest.md) |  |  |

### Return type

[**OrganizationInvitation**](OrganizationInvitation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invitation created. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **402** | Seat cap exceeded on free tier. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createorganizationworkspace"></a>
# **CreateOrganizationWorkspace**
> WorkspaceEnvelope CreateOrganizationWorkspace (string org, CreateWorkspaceRequest createWorkspaceRequest)

Create a workspace inside an organization.

Requires the `OrgActionCreateWorkspace` action permission. Slug collisions auto-suffix (`-2`, `-3`, ...). 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class CreateOrganizationWorkspaceExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var createWorkspaceRequest = new CreateWorkspaceRequest(); // CreateWorkspaceRequest | 

            try
            {
                // Create a workspace inside an organization.
                WorkspaceEnvelope result = apiInstance.CreateOrganizationWorkspace(org, createWorkspaceRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.CreateOrganizationWorkspace: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateOrganizationWorkspaceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a workspace inside an organization.
    ApiResponse<WorkspaceEnvelope> response = apiInstance.CreateOrganizationWorkspaceWithHttpInfo(org, createWorkspaceRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.CreateOrganizationWorkspaceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **createWorkspaceRequest** | [**CreateWorkspaceRequest**](CreateWorkspaceRequest.md) |  |  |

### Return type

[**WorkspaceEnvelope**](WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Workspace created. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteorganization"></a>
# **DeleteOrganization**
> void DeleteOrganization (string org)

Delete an organization.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class DeleteOrganizationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | Organization id or slug.

            try
            {
                // Delete an organization.
                apiInstance.DeleteOrganization(org);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.DeleteOrganization: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteOrganizationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete an organization.
    apiInstance.DeleteOrganizationWithHttpInfo(org);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.DeleteOrganizationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** | Organization id or slug. |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Organization deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteorganizationconcept"></a>
# **DeleteOrganizationConcept**
> void DeleteOrganizationConcept (string org, string slug)

Delete a concept (admin+ only).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class DeleteOrganizationConceptExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var slug = "slug_example";  // string | 

            try
            {
                // Delete a concept (admin+ only).
                apiInstance.DeleteOrganizationConcept(org, slug);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.DeleteOrganizationConcept: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteOrganizationConceptWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a concept (admin+ only).
    apiInstance.DeleteOrganizationConceptWithHttpInfo(org, slug);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.DeleteOrganizationConceptWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **slug** | **string** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteorganizationcustomrole"></a>
# **DeleteOrganizationCustomRole**
> void DeleteOrganizationCustomRole (string org, string roleId)

Delete a custom role (admin+ only).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class DeleteOrganizationCustomRoleExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var roleId = "roleId_example";  // string | 

            try
            {
                // Delete a custom role (admin+ only).
                apiInstance.DeleteOrganizationCustomRole(org, roleId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.DeleteOrganizationCustomRole: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteOrganizationCustomRoleWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a custom role (admin+ only).
    apiInstance.DeleteOrganizationCustomRoleWithHttpInfo(org, roleId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.DeleteOrganizationCustomRoleWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **roleId** | **string** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteorganizationlogo"></a>
# **DeleteOrganizationLogo**
> void DeleteOrganizationLogo (string org)

Delete the organization logo.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class DeleteOrganizationLogoExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 

            try
            {
                // Delete the organization logo.
                apiInstance.DeleteOrganizationLogo(org);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.DeleteOrganizationLogo: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteOrganizationLogoWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete the organization logo.
    apiInstance.DeleteOrganizationLogoWithHttpInfo(org);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.DeleteOrganizationLogoWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getorganization"></a>
# **GetOrganization**
> OrganizationDetailLegacy GetOrganization (string org)

Fetch a single organization.

**Wire format note:** response uses PascalCase keys (`ID`, `Name`, `Slug`, ...) — distinct from the rest of the SpatioAPI's camelCase convention. Documented as-is; a future cleanup will harmonize. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class GetOrganizationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | Organization id or slug.

            try
            {
                // Fetch a single organization.
                OrganizationDetailLegacy result = apiInstance.GetOrganization(org);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.GetOrganization: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetOrganizationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch a single organization.
    ApiResponse<OrganizationDetailLegacy> response = apiInstance.GetOrganizationWithHttpInfo(org);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.GetOrganizationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** | Organization id or slug. |  |

### Return type

[**OrganizationDetailLegacy**](OrganizationDetailLegacy.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The organization (PascalCase). |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not a member of this organization. |  -  |
| **404** | Organization not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getorganizationconcept"></a>
# **GetOrganizationConcept**
> Dictionary&lt;string, Object&gt; GetOrganizationConcept (string org, string slug)

Fetch a concept.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class GetOrganizationConceptExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var slug = "slug_example";  // string | 

            try
            {
                // Fetch a concept.
                Dictionary<string, Object> result = apiInstance.GetOrganizationConcept(org, slug);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.GetOrganizationConcept: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetOrganizationConceptWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch a concept.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.GetOrganizationConceptWithHttpInfo(org, slug);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.GetOrganizationConceptWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **slug** | **string** |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Concept. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listmyorganizations"></a>
# **ListMyOrganizations**
> OrganizationListResponse ListMyOrganizations ()

List the caller's organizations.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class ListMyOrganizationsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);

            try
            {
                // List the caller's organizations.
                OrganizationListResponse result = apiInstance.ListMyOrganizations();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.ListMyOrganizations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListMyOrganizationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List the caller's organizations.
    ApiResponse<OrganizationListResponse> response = apiInstance.ListMyOrganizationsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.ListMyOrganizationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**OrganizationListResponse**](OrganizationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Organization list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listorganizationauditlog"></a>
# **ListOrganizationAuditLog**
> Dictionary&lt;string, Object&gt; ListOrganizationAuditLog (string org, int? limit = null, string? cursor = null)

Read the organization audit log (admin / billing-admin only).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class ListOrganizationAuditLogExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var limit = 56;  // int? |  (optional) 
            var cursor = "cursor_example";  // string? |  (optional) 

            try
            {
                // Read the organization audit log (admin / billing-admin only).
                Dictionary<string, Object> result = apiInstance.ListOrganizationAuditLog(org, limit, cursor);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.ListOrganizationAuditLog: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListOrganizationAuditLogWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Read the organization audit log (admin / billing-admin only).
    ApiResponse<Dictionary<string, Object>> response = apiInstance.ListOrganizationAuditLogWithHttpInfo(org, limit, cursor);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.ListOrganizationAuditLogWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **limit** | **int?** |  | [optional]  |
| **cursor** | **string?** |  | [optional]  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Audit envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listorganizationconcepts"></a>
# **ListOrganizationConcepts**
> Dictionary&lt;string, Object&gt; ListOrganizationConcepts (string org)

List org-brain concepts (curated knowledge surfaced to agents).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class ListOrganizationConceptsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 

            try
            {
                // List org-brain concepts (curated knowledge surfaced to agents).
                Dictionary<string, Object> result = apiInstance.ListOrganizationConcepts(org);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.ListOrganizationConcepts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListOrganizationConceptsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List org-brain concepts (curated knowledge surfaced to agents).
    ApiResponse<Dictionary<string, Object>> response = apiInstance.ListOrganizationConceptsWithHttpInfo(org);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.ListOrganizationConceptsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Concept envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listorganizationcustomroles"></a>
# **ListOrganizationCustomRoles**
> Dictionary&lt;string, Object&gt; ListOrganizationCustomRoles (string org)

List custom roles defined on the organization.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class ListOrganizationCustomRolesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 

            try
            {
                // List custom roles defined on the organization.
                Dictionary<string, Object> result = apiInstance.ListOrganizationCustomRoles(org);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.ListOrganizationCustomRoles: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListOrganizationCustomRolesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List custom roles defined on the organization.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.ListOrganizationCustomRolesWithHttpInfo(org);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.ListOrganizationCustomRolesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Role envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listorganizationinvitations"></a>
# **ListOrganizationInvitations**
> OrganizationInvitationListResponse ListOrganizationInvitations (string org)

List pending invitations for an organization.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class ListOrganizationInvitationsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 

            try
            {
                // List pending invitations for an organization.
                OrganizationInvitationListResponse result = apiInstance.ListOrganizationInvitations(org);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.ListOrganizationInvitations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListOrganizationInvitationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List pending invitations for an organization.
    ApiResponse<OrganizationInvitationListResponse> response = apiInstance.ListOrganizationInvitationsWithHttpInfo(org);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.ListOrganizationInvitationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |

### Return type

[**OrganizationInvitationListResponse**](OrganizationInvitationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invitation list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listorganizationmembers"></a>
# **ListOrganizationMembers**
> OrganizationMemberListResponse ListOrganizationMembers (string org)

List members of an organization.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class ListOrganizationMembersExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 

            try
            {
                // List members of an organization.
                OrganizationMemberListResponse result = apiInstance.ListOrganizationMembers(org);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.ListOrganizationMembers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListOrganizationMembersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List members of an organization.
    ApiResponse<OrganizationMemberListResponse> response = apiInstance.ListOrganizationMembersWithHttpInfo(org);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.ListOrganizationMembersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |

### Return type

[**OrganizationMemberListResponse**](OrganizationMemberListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Member list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listorganizationworkspaces"></a>
# **ListOrganizationWorkspaces**
> WorkspaceListResponse ListOrganizationWorkspaces (string org)

List workspaces in an organization.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class ListOrganizationWorkspacesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 

            try
            {
                // List workspaces in an organization.
                WorkspaceListResponse result = apiInstance.ListOrganizationWorkspaces(org);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.ListOrganizationWorkspaces: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListOrganizationWorkspacesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List workspaces in an organization.
    ApiResponse<WorkspaceListResponse> response = apiInstance.ListOrganizationWorkspacesWithHttpInfo(org);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.ListOrganizationWorkspacesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |

### Return type

[**WorkspaceListResponse**](WorkspaceListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Workspace list with member counts. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not a member of this organization. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="removeorganizationmember"></a>
# **RemoveOrganizationMember**
> void RemoveOrganizationMember (string org, string memberId)

Remove a member from the organization.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class RemoveOrganizationMemberExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var memberId = "memberId_example";  // string | 

            try
            {
                // Remove a member from the organization.
                apiInstance.RemoveOrganizationMember(org, memberId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.RemoveOrganizationMember: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RemoveOrganizationMemberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Remove a member from the organization.
    apiInstance.RemoveOrganizationMemberWithHttpInfo(org, memberId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.RemoveOrganizationMemberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **memberId** | **string** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Member removed. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="resendorganizationinvitation"></a>
# **ResendOrganizationInvitation**
> OrganizationInvitation ResendOrganizationInvitation (string org, string invitationId)

Revoke and reissue an invitation with a fresh token.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class ResendOrganizationInvitationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var invitationId = "invitationId_example";  // string | 

            try
            {
                // Revoke and reissue an invitation with a fresh token.
                OrganizationInvitation result = apiInstance.ResendOrganizationInvitation(org, invitationId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.ResendOrganizationInvitation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ResendOrganizationInvitationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Revoke and reissue an invitation with a fresh token.
    ApiResponse<OrganizationInvitation> response = apiInstance.ResendOrganizationInvitationWithHttpInfo(org, invitationId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.ResendOrganizationInvitationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **invitationId** | **string** |  |  |

### Return type

[**OrganizationInvitation**](OrganizationInvitation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | New invitation. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Invitation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="revokeorganizationinvitation"></a>
# **RevokeOrganizationInvitation**
> void RevokeOrganizationInvitation (string org, string invitationId)

Revoke a pending invitation.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class RevokeOrganizationInvitationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var invitationId = "invitationId_example";  // string | 

            try
            {
                // Revoke a pending invitation.
                apiInstance.RevokeOrganizationInvitation(org, invitationId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.RevokeOrganizationInvitation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RevokeOrganizationInvitationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Revoke a pending invitation.
    apiInstance.RevokeOrganizationInvitationWithHttpInfo(org, invitationId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.RevokeOrganizationInvitationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **invitationId** | **string** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Invitation revoked. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Invitation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateorganization"></a>
# **UpdateOrganization**
> Dictionary&lt;string, Object&gt; UpdateOrganization (string org, UpdateOrganizationRequest updateOrganizationRequest)

Update organization metadata.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class UpdateOrganizationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | Organization id or slug.
            var updateOrganizationRequest = new UpdateOrganizationRequest(); // UpdateOrganizationRequest | 

            try
            {
                // Update organization metadata.
                Dictionary<string, Object> result = apiInstance.UpdateOrganization(org, updateOrganizationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.UpdateOrganization: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateOrganizationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update organization metadata.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.UpdateOrganizationWithHttpInfo(org, updateOrganizationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.UpdateOrganizationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** | Organization id or slug. |  |
| **updateOrganizationRequest** | [**UpdateOrganizationRequest**](UpdateOrganizationRequest.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated org. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateorganizationconcept"></a>
# **UpdateOrganizationConcept**
> Dictionary&lt;string, Object&gt; UpdateOrganizationConcept (string org, string slug, Dictionary<string, Object> requestBody)

Update a concept (admin+ only).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class UpdateOrganizationConceptExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var slug = "slug_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                // Update a concept (admin+ only).
                Dictionary<string, Object> result = apiInstance.UpdateOrganizationConcept(org, slug, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.UpdateOrganizationConcept: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateOrganizationConceptWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a concept (admin+ only).
    ApiResponse<Dictionary<string, Object>> response = apiInstance.UpdateOrganizationConceptWithHttpInfo(org, slug, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.UpdateOrganizationConceptWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **slug** | **string** |  |  |
| **requestBody** | [**Dictionary&lt;string, Object&gt;**](Object.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateorganizationcustomrole"></a>
# **UpdateOrganizationCustomRole**
> Dictionary&lt;string, Object&gt; UpdateOrganizationCustomRole (string org, string roleId, Dictionary<string, Object> requestBody)

Update a custom role (admin+ only).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class UpdateOrganizationCustomRoleExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var roleId = "roleId_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                // Update a custom role (admin+ only).
                Dictionary<string, Object> result = apiInstance.UpdateOrganizationCustomRole(org, roleId, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.UpdateOrganizationCustomRole: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateOrganizationCustomRoleWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a custom role (admin+ only).
    ApiResponse<Dictionary<string, Object>> response = apiInstance.UpdateOrganizationCustomRoleWithHttpInfo(org, roleId, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.UpdateOrganizationCustomRoleWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **roleId** | **string** |  |  |
| **requestBody** | [**Dictionary&lt;string, Object&gt;**](Object.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateorganizationmember"></a>
# **UpdateOrganizationMember**
> Dictionary&lt;string, Object&gt; UpdateOrganizationMember (string org, string memberId, UpdateOrganizationMemberRequest updateOrganizationMemberRequest)

Update a member's role.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class UpdateOrganizationMemberExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var memberId = "memberId_example";  // string | 
            var updateOrganizationMemberRequest = new UpdateOrganizationMemberRequest(); // UpdateOrganizationMemberRequest | 

            try
            {
                // Update a member's role.
                Dictionary<string, Object> result = apiInstance.UpdateOrganizationMember(org, memberId, updateOrganizationMemberRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.UpdateOrganizationMember: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateOrganizationMemberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a member's role.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.UpdateOrganizationMemberWithHttpInfo(org, memberId, updateOrganizationMemberRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.UpdateOrganizationMemberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **memberId** | **string** |  |  |
| **updateOrganizationMemberRequest** | [**UpdateOrganizationMemberRequest**](UpdateOrganizationMemberRequest.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Member updated. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="uploadorganizationlogo"></a>
# **UploadOrganizationLogo**
> Dictionary&lt;string, Object&gt; UploadOrganizationLogo (string org, FileParameter? file = null)

Upload (or replace) the organization logo. Multipart.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Spatio.Sdk.Api;
using Spatio.Sdk.Client;
using Spatio.Sdk.Model;

namespace Example
{
    public class UploadOrganizationLogoExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new OrganizationsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var file = new System.IO.MemoryStream(System.IO.File.ReadAllBytes("/path/to/file.txt"));  // FileParameter? |  (optional) 

            try
            {
                // Upload (or replace) the organization logo. Multipart.
                Dictionary<string, Object> result = apiInstance.UploadOrganizationLogo(org, file);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling OrganizationsApi.UploadOrganizationLogo: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UploadOrganizationLogoWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Upload (or replace) the organization logo. Multipart.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.UploadOrganizationLogoWithHttpInfo(org, file);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling OrganizationsApi.UploadOrganizationLogoWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **file** | **FileParameter?****FileParameter?** |  | [optional]  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Uploaded. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

