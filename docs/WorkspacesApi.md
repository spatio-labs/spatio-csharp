# Spatio.Sdk.Api.WorkspacesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AcceptWorkspaceInvitation**](WorkspacesApi.md#acceptworkspaceinvitation) | **POST** /v1/invitations/{token}/accept | Accept a workspace invitation by token. The signed-in user&#39;s email must match the invitation. Organization-token accept lives at &#x60;POST /v1/organizations/{org}/accept-invitation&#x60;.  |
| [**AddWorkspaceMember**](WorkspacesApi.md#addworkspacemember) | **POST** /v1/workspaces/{workspaceId}/members | Add a member directly (skips invitation flow). |
| [**CreateWorkspace**](WorkspacesApi.md#createworkspace) | **POST** /v1/workspaces | Create a workspace. Requires &#x60;organizationId&#x60; in the body — bare \&quot;personal\&quot; workspaces aren&#39;t supported on the public API.  |
| [**CreateWorkspaceInvitation**](WorkspacesApi.md#createworkspaceinvitation) | **POST** /v1/workspaces/{workspaceId}/invitations | Invite a user to a workspace. |
| [**GetPublicInvitation**](WorkspacesApi.md#getpublicinvitation) | **GET** /invitations/{token} | Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in.  |
| [**GetWorkspace**](WorkspacesApi.md#getworkspace) | **GET** /v1/workspaces/{workspaceId} | Fetch a single workspace by id. |
| [**ListMyWorkspaces**](WorkspacesApi.md#listmyworkspaces) | **GET** /v1/workspaces | List the caller&#39;s workspaces (across organizations). |
| [**ListWorkspaceInvitations**](WorkspacesApi.md#listworkspaceinvitations) | **GET** /v1/workspaces/{workspaceId}/invitations | List pending workspace invitations. |
| [**ListWorkspaceMembers**](WorkspacesApi.md#listworkspacemembers) | **GET** /v1/workspaces/{workspaceId}/members | List members of a workspace. |
| [**RemoveWorkspaceMember**](WorkspacesApi.md#removeworkspacemember) | **DELETE** /v1/workspaces/{workspaceId}/members/{memberId} | Remove a member from the workspace. |
| [**RevokeWorkspaceInvitation**](WorkspacesApi.md#revokeworkspaceinvitation) | **DELETE** /v1/workspaces/{workspaceId}/invitations/{invitationId} | Revoke a pending workspace invitation. |
| [**UpdateWorkspace**](WorkspacesApi.md#updateworkspace) | **PATCH** /v1/workspaces/{workspaceId} | Update workspace metadata. |
| [**UpdateWorkspaceMember**](WorkspacesApi.md#updateworkspacemember) | **PATCH** /v1/workspaces/{workspaceId}/members/{memberId} | Update a member&#39;s role. |

<a id="acceptworkspaceinvitation"></a>
# **AcceptWorkspaceInvitation**
> Dictionary&lt;string, Object&gt; AcceptWorkspaceInvitation (string token)

Accept a workspace invitation by token. The signed-in user's email must match the invitation. Organization-token accept lives at `POST /v1/organizations/{org}/accept-invitation`. 

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
    public class AcceptWorkspaceInvitationExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var token = "token_example";  // string | 

            try
            {
                // Accept a workspace invitation by token. The signed-in user's email must match the invitation. Organization-token accept lives at `POST /v1/organizations/{org}/accept-invitation`. 
                Dictionary<string, Object> result = apiInstance.AcceptWorkspaceInvitation(token);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.AcceptWorkspaceInvitation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the AcceptWorkspaceInvitationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Accept a workspace invitation by token. The signed-in user's email must match the invitation. Organization-token accept lives at `POST /v1/organizations/{org}/accept-invitation`. 
    ApiResponse<Dictionary<string, Object>> response = apiInstance.AcceptWorkspaceInvitationWithHttpInfo(token);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.AcceptWorkspaceInvitationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **token** | **string** |  |  |

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
| **200** | Invitation accepted. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Invitation not found. |  -  |
| **410** | Invitation already accepted, revoked, or expired. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="addworkspacemember"></a>
# **AddWorkspaceMember**
> Dictionary&lt;string, Object&gt; AddWorkspaceMember (string workspaceId, AddWorkspaceMemberRequest addWorkspaceMemberRequest)

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
    public class AddWorkspaceMemberExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var workspaceId = "workspaceId_example";  // string | 
            var addWorkspaceMemberRequest = new AddWorkspaceMemberRequest(); // AddWorkspaceMemberRequest | 

            try
            {
                // Add a member directly (skips invitation flow).
                Dictionary<string, Object> result = apiInstance.AddWorkspaceMember(workspaceId, addWorkspaceMemberRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.AddWorkspaceMember: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the AddWorkspaceMemberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Add a member directly (skips invitation flow).
    ApiResponse<Dictionary<string, Object>> response = apiInstance.AddWorkspaceMemberWithHttpInfo(workspaceId, addWorkspaceMemberRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.AddWorkspaceMemberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **workspaceId** | **string** |  |  |
| **addWorkspaceMemberRequest** | [**AddWorkspaceMemberRequest**](AddWorkspaceMemberRequest.md) |  |  |

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
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createworkspace"></a>
# **CreateWorkspace**
> WorkspaceEnvelope CreateWorkspace (CreateWorkspaceRequest createWorkspaceRequest)

Create a workspace. Requires `organizationId` in the body — bare \"personal\" workspaces aren't supported on the public API. 

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
    public class CreateWorkspaceExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var createWorkspaceRequest = new CreateWorkspaceRequest(); // CreateWorkspaceRequest | 

            try
            {
                // Create a workspace. Requires `organizationId` in the body — bare \"personal\" workspaces aren't supported on the public API. 
                WorkspaceEnvelope result = apiInstance.CreateWorkspace(createWorkspaceRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.CreateWorkspace: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWorkspaceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a workspace. Requires `organizationId` in the body — bare \"personal\" workspaces aren't supported on the public API. 
    ApiResponse<WorkspaceEnvelope> response = apiInstance.CreateWorkspaceWithHttpInfo(createWorkspaceRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.CreateWorkspaceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
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
| **400** | Invalid body or missing organizationId. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role in the target organization. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createworkspaceinvitation"></a>
# **CreateWorkspaceInvitation**
> WorkspaceInvitation CreateWorkspaceInvitation (string workspaceId, CreateWorkspaceInvitationRequest createWorkspaceInvitationRequest)

Invite a user to a workspace.

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
    public class CreateWorkspaceInvitationExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var workspaceId = "workspaceId_example";  // string | 
            var createWorkspaceInvitationRequest = new CreateWorkspaceInvitationRequest(); // CreateWorkspaceInvitationRequest | 

            try
            {
                // Invite a user to a workspace.
                WorkspaceInvitation result = apiInstance.CreateWorkspaceInvitation(workspaceId, createWorkspaceInvitationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.CreateWorkspaceInvitation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWorkspaceInvitationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Invite a user to a workspace.
    ApiResponse<WorkspaceInvitation> response = apiInstance.CreateWorkspaceInvitationWithHttpInfo(workspaceId, createWorkspaceInvitationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.CreateWorkspaceInvitationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **workspaceId** | **string** |  |  |
| **createWorkspaceInvitationRequest** | [**CreateWorkspaceInvitationRequest**](CreateWorkspaceInvitationRequest.md) |  |  |

### Return type

[**WorkspaceInvitation**](WorkspaceInvitation.md)

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

<a id="getpublicinvitation"></a>
# **GetPublicInvitation**
> PublicInvitationPayload GetPublicInvitation (string token)

Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in. 

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
    public class GetPublicInvitationExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var token = "token_example";  // string | 

            try
            {
                // Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in. 
                PublicInvitationPayload result = apiInstance.GetPublicInvitation(token);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.GetPublicInvitation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPublicInvitationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in. 
    ApiResponse<PublicInvitationPayload> response = apiInstance.GetPublicInvitationWithHttpInfo(token);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.GetPublicInvitationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **token** | **string** |  |  |

### Return type

[**PublicInvitationPayload**](PublicInvitationPayload.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invitation payload (workspace or organization). |  -  |
| **404** | Invitation not found. |  -  |
| **410** | Invitation already accepted, revoked, or expired. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getworkspace"></a>
# **GetWorkspace**
> WorkspaceEnvelope GetWorkspace (string workspaceId)

Fetch a single workspace by id.

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
    public class GetWorkspaceExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var workspaceId = "workspaceId_example";  // string | 

            try
            {
                // Fetch a single workspace by id.
                WorkspaceEnvelope result = apiInstance.GetWorkspace(workspaceId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.GetWorkspace: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWorkspaceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch a single workspace by id.
    ApiResponse<WorkspaceEnvelope> response = apiInstance.GetWorkspaceWithHttpInfo(workspaceId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.GetWorkspaceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **workspaceId** | **string** |  |  |

### Return type

[**WorkspaceEnvelope**](WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Workspace envelope. The &#x60;workspace&#x60; payload includes a compact &#x60;organization&#x60; summary and the caller&#39;s &#x60;role&#x60;.  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not a member of this workspace. |  -  |
| **404** | Workspace not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listmyworkspaces"></a>
# **ListMyWorkspaces**
> WorkspaceListResponse ListMyWorkspaces ()

List the caller's workspaces (across organizations).

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
    public class ListMyWorkspacesExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);

            try
            {
                // List the caller's workspaces (across organizations).
                WorkspaceListResponse result = apiInstance.ListMyWorkspaces();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.ListMyWorkspaces: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListMyWorkspacesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List the caller's workspaces (across organizations).
    ApiResponse<WorkspaceListResponse> response = apiInstance.ListMyWorkspacesWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.ListMyWorkspacesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
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
| **200** | Workspace list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listworkspaceinvitations"></a>
# **ListWorkspaceInvitations**
> WorkspaceInvitationListResponse ListWorkspaceInvitations (string workspaceId)

List pending workspace invitations.

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
    public class ListWorkspaceInvitationsExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var workspaceId = "workspaceId_example";  // string | 

            try
            {
                // List pending workspace invitations.
                WorkspaceInvitationListResponse result = apiInstance.ListWorkspaceInvitations(workspaceId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.ListWorkspaceInvitations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWorkspaceInvitationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List pending workspace invitations.
    ApiResponse<WorkspaceInvitationListResponse> response = apiInstance.ListWorkspaceInvitationsWithHttpInfo(workspaceId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.ListWorkspaceInvitationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **workspaceId** | **string** |  |  |

### Return type

[**WorkspaceInvitationListResponse**](WorkspaceInvitationListResponse.md)

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

<a id="listworkspacemembers"></a>
# **ListWorkspaceMembers**
> WorkspaceMemberListResponse ListWorkspaceMembers (string workspaceId)

List members of a workspace.

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
    public class ListWorkspaceMembersExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var workspaceId = "workspaceId_example";  // string | 

            try
            {
                // List members of a workspace.
                WorkspaceMemberListResponse result = apiInstance.ListWorkspaceMembers(workspaceId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.ListWorkspaceMembers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWorkspaceMembersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List members of a workspace.
    ApiResponse<WorkspaceMemberListResponse> response = apiInstance.ListWorkspaceMembersWithHttpInfo(workspaceId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.ListWorkspaceMembersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **workspaceId** | **string** |  |  |

### Return type

[**WorkspaceMemberListResponse**](WorkspaceMemberListResponse.md)

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

<a id="removeworkspacemember"></a>
# **RemoveWorkspaceMember**
> void RemoveWorkspaceMember (string workspaceId, string memberId)

Remove a member from the workspace.

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
    public class RemoveWorkspaceMemberExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var workspaceId = "workspaceId_example";  // string | 
            var memberId = "memberId_example";  // string | 

            try
            {
                // Remove a member from the workspace.
                apiInstance.RemoveWorkspaceMember(workspaceId, memberId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.RemoveWorkspaceMember: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RemoveWorkspaceMemberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Remove a member from the workspace.
    apiInstance.RemoveWorkspaceMemberWithHttpInfo(workspaceId, memberId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.RemoveWorkspaceMemberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **workspaceId** | **string** |  |  |
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

<a id="revokeworkspaceinvitation"></a>
# **RevokeWorkspaceInvitation**
> void RevokeWorkspaceInvitation (string workspaceId, string invitationId)

Revoke a pending workspace invitation.

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
    public class RevokeWorkspaceInvitationExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var workspaceId = "workspaceId_example";  // string | 
            var invitationId = "invitationId_example";  // string | 

            try
            {
                // Revoke a pending workspace invitation.
                apiInstance.RevokeWorkspaceInvitation(workspaceId, invitationId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.RevokeWorkspaceInvitation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RevokeWorkspaceInvitationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Revoke a pending workspace invitation.
    apiInstance.RevokeWorkspaceInvitationWithHttpInfo(workspaceId, invitationId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.RevokeWorkspaceInvitationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **workspaceId** | **string** |  |  |
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

<a id="updateworkspace"></a>
# **UpdateWorkspace**
> WorkspaceEnvelope UpdateWorkspace (string workspaceId, UpdateWorkspaceRequest updateWorkspaceRequest)

Update workspace metadata.

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
    public class UpdateWorkspaceExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var workspaceId = "workspaceId_example";  // string | 
            var updateWorkspaceRequest = new UpdateWorkspaceRequest(); // UpdateWorkspaceRequest | 

            try
            {
                // Update workspace metadata.
                WorkspaceEnvelope result = apiInstance.UpdateWorkspace(workspaceId, updateWorkspaceRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.UpdateWorkspace: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateWorkspaceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update workspace metadata.
    ApiResponse<WorkspaceEnvelope> response = apiInstance.UpdateWorkspaceWithHttpInfo(workspaceId, updateWorkspaceRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.UpdateWorkspaceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **workspaceId** | **string** |  |  |
| **updateWorkspaceRequest** | [**UpdateWorkspaceRequest**](UpdateWorkspaceRequest.md) |  |  |

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
| **200** | Updated workspace envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateworkspacemember"></a>
# **UpdateWorkspaceMember**
> Dictionary&lt;string, Object&gt; UpdateWorkspaceMember (string workspaceId, string memberId, UpdateWorkspaceMemberRequest updateWorkspaceMemberRequest)

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
    public class UpdateWorkspaceMemberExample
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
            var apiInstance = new WorkspacesApi(httpClient, config, httpClientHandler);
            var workspaceId = "workspaceId_example";  // string | 
            var memberId = "memberId_example";  // string | 
            var updateWorkspaceMemberRequest = new UpdateWorkspaceMemberRequest(); // UpdateWorkspaceMemberRequest | 

            try
            {
                // Update a member's role.
                Dictionary<string, Object> result = apiInstance.UpdateWorkspaceMember(workspaceId, memberId, updateWorkspaceMemberRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WorkspacesApi.UpdateWorkspaceMember: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateWorkspaceMemberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a member's role.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.UpdateWorkspaceMemberWithHttpInfo(workspaceId, memberId, updateWorkspaceMemberRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WorkspacesApi.UpdateWorkspaceMemberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **workspaceId** | **string** |  |  |
| **memberId** | **string** |  |  |
| **updateWorkspaceMemberRequest** | [**UpdateWorkspaceMemberRequest**](UpdateWorkspaceMemberRequest.md) |  |  |

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

