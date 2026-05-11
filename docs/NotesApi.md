# Spatio.Sdk.Api.NotesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateBlock**](NotesApi.md#createblock) | **POST** /v1/notes/{id}/blocks | Insert a block in a note. |
| [**CreateNote**](NotesApi.md#createnote) | **POST** /v1/notes | Create a note. |
| [**CreateNoteComment**](NotesApi.md#createnotecomment) | **POST** /v1/notes/{id}/comments | Create a comment or reply. |
| [**DeleteBlock**](NotesApi.md#deleteblock) | **DELETE** /v1/notes/blocks/{id} | Delete a block. |
| [**DeleteNote**](NotesApi.md#deletenote) | **DELETE** /v1/notes/{id} | Delete a note. |
| [**DeleteNoteComment**](NotesApi.md#deletenotecomment) | **DELETE** /v1/notes/{id}/comments/{commentId} | Soft-delete (native) or hard-delete (provider) a comment. |
| [**DisableNoteShare**](NotesApi.md#disablenoteshare) | **DELETE** /v1/notes/{id}/share | Disable public sharing. |
| [**EnableNoteShare**](NotesApi.md#enablenoteshare) | **POST** /v1/notes/{id}/share | Enable (or update password on) public sharing. |
| [**GetBlock**](NotesApi.md#getblock) | **GET** /v1/notes/blocks/{id} | Fetch one block. |
| [**GetNote**](NotesApi.md#getnote) | **GET** /v1/notes/{id} | Fetch one note. |
| [**GetNoteComment**](NotesApi.md#getnotecomment) | **GET** /v1/notes/{id}/comments/{commentId} | Fetch one comment. |
| [**GetNoteShareSettings**](NotesApi.md#getnotesharesettings) | **GET** /v1/notes/{id}/share | Fetch share settings for a note. |
| [**GetPublicNote**](NotesApi.md#getpublicnote) | **GET** /public/notes/{token} | Fetch a publicly shared note. |
| [**ListBlocks**](NotesApi.md#listblocks) | **GET** /v1/notes/{id}/blocks | List blocks under a note. |
| [**ListNoteComments**](NotesApi.md#listnotecomments) | **GET** /v1/notes/{id}/comments | List comments on a note. |
| [**ListNotes**](NotesApi.md#listnotes) | **GET** /v1/notes | List notes across connected accounts. |
| [**MoveBlock**](NotesApi.md#moveblock) | **POST** /v1/notes/blocks/{id}/move | Reparent or reorder a block. |
| [**RotateNoteShareToken**](NotesApi.md#rotatenotesharetoken) | **POST** /v1/notes/{id}/share/rotate | Rotate the share token, invalidating any outstanding URLs. |
| [**UpdateBlock**](NotesApi.md#updateblock) | **PATCH** /v1/notes/blocks/{id} | Update a block (partial). |
| [**UpdateNote**](NotesApi.md#updatenote) | **PATCH** /v1/notes/{id} | Update a note (partial). |
| [**UpdateNoteComment**](NotesApi.md#updatenotecomment) | **PATCH** /v1/notes/{id}/comments/{commentId} | Edit a comment. |
| [**WorkspaceCreateNote**](NotesApi.md#workspacecreatenote) | **POST** /v1/organizations/{org}/workspaces/{workspace}/notes |  |
| [**WorkspaceCreateNoteBlock**](NotesApi.md#workspacecreatenoteblock) | **POST** /v1/organizations/{org}/workspaces/{workspace}/notes/{id}/blocks |  |
| [**WorkspaceDeleteNote**](NotesApi.md#workspacedeletenote) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/notes/{id} |  |
| [**WorkspaceDeleteNoteBlock**](NotesApi.md#workspacedeletenoteblock) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id} |  |
| [**WorkspaceGetNote**](NotesApi.md#workspacegetnote) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes/{id} |  |
| [**WorkspaceGetNoteBlock**](NotesApi.md#workspacegetnoteblock) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id} |  |
| [**WorkspaceListNoteBlocks**](NotesApi.md#workspacelistnoteblocks) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes/{id}/blocks |  |
| [**WorkspaceListNotes**](NotesApi.md#workspacelistnotes) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes |  |
| [**WorkspaceMoveNoteBlock**](NotesApi.md#workspacemovenoteblock) | **POST** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id}/move |  |
| [**WorkspaceUpdateNote**](NotesApi.md#workspaceupdatenote) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/notes/{id} |  |
| [**WorkspaceUpdateNoteBlock**](NotesApi.md#workspaceupdatenoteblock) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id} |  |

<a id="createblock"></a>
# **CreateBlock**
> Block CreateBlock (string id, CreateBlockRequest createBlockRequest, string? accountId = null, string? xWorkspaceID = null)

Insert a block in a note.

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
    public class CreateBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var createBlockRequest = new CreateBlockRequest(); // CreateBlockRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Insert a block in a note.
                Block result = apiInstance.CreateBlock(id, createBlockRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.CreateBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Insert a block in a note.
    ApiResponse<Block> response = apiInstance.CreateBlockWithHttpInfo(id, createBlockRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.CreateBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **createBlockRequest** | [**CreateBlockRequest**](CreateBlockRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Block**](Block.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Block created. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Note not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createnote"></a>
# **CreateNote**
> Note CreateNote (CreateNoteRequest createNoteRequest, string? accountId = null, string? provider = null, string? xWorkspaceID = null)

Create a note.

Creates a new note under the target account. The target is resolved in this order: `accountId` field on the body → `?accountId=` query → `provider` field on the body → `?provider=` query → the caller's single connected account (errors with `ambiguous_account` if more than one is connected and no selector is supplied). 

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
    public class CreateNoteExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var createNoteRequest = new CreateNoteRequest(); // CreateNoteRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var provider = "provider_example";  // string? | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Create a note.
                Note result = apiInstance.CreateNote(createNoteRequest, accountId, provider, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.CreateNote: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateNoteWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a note.
    ApiResponse<Note> response = apiInstance.CreateNoteWithHttpInfo(createNoteRequest, accountId, provider, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.CreateNoteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createNoteRequest** | [**CreateNoteRequest**](CreateNoteRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **provider** | **string?** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Note**](Note.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Note created. |  -  |
| **400** | Invalid body, or no selector supplied with multiple connected accounts (&#x60;code: ambiguous_account&#x60;), or no notes provider connected (&#x60;code: no_notes_provider&#x60;).  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createnotecomment"></a>
# **CreateNoteComment**
> CommentMutationResponse CreateNoteComment (string id, CreateCommentRequest createCommentRequest, string? accountId = null, string? xWorkspaceID = null)

Create a comment or reply.

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
    public class CreateNoteCommentExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var createCommentRequest = new CreateCommentRequest(); // CreateCommentRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Create a comment or reply.
                CommentMutationResponse result = apiInstance.CreateNoteComment(id, createCommentRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.CreateNoteComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateNoteCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a comment or reply.
    ApiResponse<CommentMutationResponse> response = apiInstance.CreateNoteCommentWithHttpInfo(id, createCommentRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.CreateNoteCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **createCommentRequest** | [**CreateCommentRequest**](CreateCommentRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**CommentMutationResponse**](CommentMutationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment created. |  -  |
| **400** | Missing body or note id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteblock"></a>
# **DeleteBlock**
> SuccessFlag DeleteBlock (string id, string? accountId = null, string? xWorkspaceID = null)

Delete a block.

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
    public class DeleteBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Block id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Delete a block.
                SuccessFlag result = apiInstance.DeleteBlock(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.DeleteBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a block.
    ApiResponse<SuccessFlag> response = apiInstance.DeleteBlockWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.DeleteBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Block id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Block not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletenote"></a>
# **DeleteNote**
> SuccessFlag DeleteNote (string id, string? accountId = null, string? xWorkspaceID = null)

Delete a note.

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
    public class DeleteNoteExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Delete a note.
                SuccessFlag result = apiInstance.DeleteNote(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.DeleteNote: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteNoteWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a note.
    ApiResponse<SuccessFlag> response = apiInstance.DeleteNoteWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.DeleteNoteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Note not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletenotecomment"></a>
# **DeleteNoteComment**
> SuccessFlag DeleteNoteComment (string id, string commentId, string? accountId = null, string? xWorkspaceID = null)

Soft-delete (native) or hard-delete (provider) a comment.

Allowed for the comment author and for the note owner. 

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
    public class DeleteNoteCommentExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var commentId = "commentId_example";  // string | Comment id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Soft-delete (native) or hard-delete (provider) a comment.
                SuccessFlag result = apiInstance.DeleteNoteComment(id, commentId, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.DeleteNoteComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteNoteCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Soft-delete (native) or hard-delete (provider) a comment.
    ApiResponse<SuccessFlag> response = apiInstance.DeleteNoteCommentWithHttpInfo(id, commentId, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.DeleteNoteCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **commentId** | **string** | Comment id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **400** | Missing comment id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is neither the author nor the note owner. |  -  |
| **404** | Comment not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="disablenoteshare"></a>
# **DisableNoteShare**
> void DisableNoteShare (string id, string? accountId = null, string? xWorkspaceID = null)

Disable public sharing.

Owner-only. Subsequent public viewer requests 404.

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
    public class DisableNoteShareExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Disable public sharing.
                apiInstance.DisableNoteShare(id, accountId, xWorkspaceID);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.DisableNoteShare: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DisableNoteShareWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Disable public sharing.
    apiInstance.DisableNoteShareWithHttpInfo(id, accountId, xWorkspaceID);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.DisableNoteShareWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

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
| **204** | Sharing disabled. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the note owner. |  -  |
| **404** | Note not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="enablenoteshare"></a>
# **EnableNoteShare**
> ShareSettings EnableNoteShare (string id, string? accountId = null, string? xWorkspaceID = null, EnableShareRequest? enableShareRequest = null)

Enable (or update password on) public sharing.

Owner-only. Calling with an empty body or `setPassword: false` flips the note public without changing the password. With `setPassword: true`, applies `password` (empty string clears). 

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
    public class EnableNoteShareExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 
            var enableShareRequest = new EnableShareRequest?(); // EnableShareRequest? |  (optional) 

            try
            {
                // Enable (or update password on) public sharing.
                ShareSettings result = apiInstance.EnableNoteShare(id, accountId, xWorkspaceID, enableShareRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.EnableNoteShare: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the EnableNoteShareWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Enable (or update password on) public sharing.
    ApiResponse<ShareSettings> response = apiInstance.EnableNoteShareWithHttpInfo(id, accountId, xWorkspaceID, enableShareRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.EnableNoteShareWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |
| **enableShareRequest** | [**EnableShareRequest?**](EnableShareRequest?.md) |  | [optional]  |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated share settings. |  -  |
| **400** | Password failed strength check. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the note owner. |  -  |
| **404** | Note not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getblock"></a>
# **GetBlock**
> Block GetBlock (string id, string? accountId = null, string? xWorkspaceID = null)

Fetch one block.

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
    public class GetBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Block id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Fetch one block.
                Block result = apiInstance.GetBlock(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.GetBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch one block.
    ApiResponse<Block> response = apiInstance.GetBlockWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.GetBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Block id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Block**](Block.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The block. |  -  |
| **400** | Missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Block not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getnote"></a>
# **GetNote**
> Note GetNote (string id, string? accountId = null, string? xWorkspaceID = null)

Fetch one note.

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
    public class GetNoteExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Fetch one note.
                Note result = apiInstance.GetNote(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.GetNote: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetNoteWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch one note.
    ApiResponse<Note> response = apiInstance.GetNoteWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.GetNoteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Note**](Note.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The note. |  -  |
| **400** | Missing id or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Note not found (&#x60;code: note_not_found&#x60;). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getnotecomment"></a>
# **GetNoteComment**
> CommentResponse GetNoteComment (string id, string commentId, string? accountId = null, string? xWorkspaceID = null)

Fetch one comment.

Useful for permalink hydration when the renderer deep-links into a reply thread. 

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
    public class GetNoteCommentExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var commentId = "commentId_example";  // string | Comment id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Fetch one comment.
                CommentResponse result = apiInstance.GetNoteComment(id, commentId, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.GetNoteComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetNoteCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch one comment.
    ApiResponse<CommentResponse> response = apiInstance.GetNoteCommentWithHttpInfo(id, commentId, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.GetNoteCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **commentId** | **string** | Comment id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**CommentResponse**](CommentResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Single comment. |  -  |
| **400** | Missing comment id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Comment not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getnotesharesettings"></a>
# **GetNoteShareSettings**
> ShareSettings GetNoteShareSettings (string id, string? accountId = null, string? xWorkspaceID = null)

Fetch share settings for a note.

Owner-only. Returns the current public-share configuration, including the share token and computed public viewer URL when the note is currently public. 

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
    public class GetNoteShareSettingsExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Fetch share settings for a note.
                ShareSettings result = apiInstance.GetNoteShareSettings(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.GetNoteShareSettings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetNoteShareSettingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch share settings for a note.
    ApiResponse<ShareSettings> response = apiInstance.GetNoteShareSettingsWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.GetNoteShareSettingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Current share settings. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the note owner. |  -  |
| **404** | Note not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getpublicnote"></a>
# **GetPublicNote**
> Dictionary&lt;string, Object&gt; GetPublicNote (string token, string? password = null)

Fetch a publicly shared note.

Unauthenticated. The share token is the credential. For password-protected notes the password is supplied via the `?password=` query param; the response distinguishes \"no password supplied\" from \"wrong password\" so the viewer can render the right prompt.  Unknown tokens and disabled-share notes both return `404` to prevent token enumeration. 

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
    public class GetPublicNoteExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var token = "token_example";  // string | Opaque public-share token.
            var password = "password_example";  // string? | Optional viewer password. (optional) 

            try
            {
                // Fetch a publicly shared note.
                Dictionary<string, Object> result = apiInstance.GetPublicNote(token, password);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.GetPublicNote: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPublicNoteWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch a publicly shared note.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.GetPublicNoteWithHttpInfo(token, password);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.GetPublicNoteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **token** | **string** | Opaque public-share token. |  |
| **password** | **string?** | Optional viewer password. | [optional]  |

### Return type

**Dictionary<string, Object>**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Read-only snapshot of the shared note. |  -  |
| **400** | Missing token. |  -  |
| **401** | Password-protected note. &#x60;requiresPassword: true&#x60; always set; &#x60;invalidPassword: true&#x60; only when a password was supplied and rejected.  |  -  |
| **404** | Token unknown or sharing disabled. |  -  |
| **500** | Snapshot rendering failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listblocks"></a>
# **ListBlocks**
> BlockListResponse ListBlocks (string id, string? accountId = null, string? xWorkspaceID = null, string? parentId = null, int? limit = null, int? offset = null)

List blocks under a note.

Returns the block tree for a note, paginated. Block listing always targets a single account (the one that owns the note) so it does not fan out — the response is a plain `{ blocks, total }`. 

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
    public class ListBlocksExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 
            var parentId = "parentId_example";  // string? | Filter to children of this block id. Omit to list root-level blocks.  (optional) 
            var limit = 100;  // int? |  (optional)  (default to 100)
            var offset = 0;  // int? |  (optional)  (default to 0)

            try
            {
                // List blocks under a note.
                BlockListResponse result = apiInstance.ListBlocks(id, accountId, xWorkspaceID, parentId, limit, offset);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.ListBlocks: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListBlocksWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List blocks under a note.
    ApiResponse<BlockListResponse> response = apiInstance.ListBlocksWithHttpInfo(id, accountId, xWorkspaceID, parentId, limit, offset);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.ListBlocksWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |
| **parentId** | **string?** | Filter to children of this block id. Omit to list root-level blocks.  | [optional]  |
| **limit** | **int?** |  | [optional] [default to 100] |
| **offset** | **int?** |  | [optional] [default to 0] |

### Return type

[**BlockListResponse**](BlockListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Block list. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Note not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listnotecomments"></a>
# **ListNoteComments**
> CommentListResponse ListNoteComments (string id, string? accountId = null, string? xWorkspaceID = null)

List comments on a note.

Returns active (non-deleted) comments. When `?accountId=` targets an external provider that supports comments (e.g. Notion), the provider is queried directly; otherwise the native store is used. 

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
    public class ListNoteCommentsExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // List comments on a note.
                CommentListResponse result = apiInstance.ListNoteComments(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.ListNoteComments: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListNoteCommentsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List comments on a note.
    ApiResponse<CommentListResponse> response = apiInstance.ListNoteCommentsWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.ListNoteCommentsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**CommentListResponse**](CommentListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment list. |  -  |
| **400** | Missing note id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listnotes"></a>
# **ListNotes**
> NoteListEnvelope ListNotes (string? accountId = null, string? provider = null, string? xWorkspaceID = null, bool? archived = null, string? parentId = null, List<string>? tags = null, int? limit = null, int? offset = null, string? sortBy = null, string? sortOrder = null)

List notes across connected accounts.

Fan-out list. Returns every note visible to the caller across every connected notes provider, paginated by `limit` / `offset`. Pass `?accountId=` or `?provider=` to scope to a single source. 

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
    public class ListNotesExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var provider = "provider_example";  // string? | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 
            var archived = false;  // bool? | When `true`, return archived notes instead of active ones. (optional)  (default to false)
            var parentId = "parentId_example";  // string? | Filter to notes nested under this parent note id. (optional) 
            var tags = new List<string>?(); // List<string>? | Repeatable. Filter to notes carrying every tag listed. (optional) 
            var limit = 50;  // int? | Max items to return. Defaults to 50. (optional)  (default to 50)
            var offset = 0;  // int? | Number of items to skip. (optional)  (default to 0)
            var sortBy = "\"updated_at\"";  // string? | Sort field. Provider-dependent; the native provider supports `updated_at`, `created_at`, `title`.  (optional)  (default to "updated_at")
            var sortOrder = "asc";  // string? |  (optional)  (default to desc)

            try
            {
                // List notes across connected accounts.
                NoteListEnvelope result = apiInstance.ListNotes(accountId, provider, xWorkspaceID, archived, parentId, tags, limit, offset, sortBy, sortOrder);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.ListNotes: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListNotesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List notes across connected accounts.
    ApiResponse<NoteListEnvelope> response = apiInstance.ListNotesWithHttpInfo(accountId, provider, xWorkspaceID, archived, parentId, tags, limit, offset, sortBy, sortOrder);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.ListNotesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **provider** | **string?** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |
| **archived** | **bool?** | When &#x60;true&#x60;, return archived notes instead of active ones. | [optional] [default to false] |
| **parentId** | **string?** | Filter to notes nested under this parent note id. | [optional]  |
| **tags** | [**List&lt;string&gt;?**](string.md) | Repeatable. Filter to notes carrying every tag listed. | [optional]  |
| **limit** | **int?** | Max items to return. Defaults to 50. | [optional] [default to 50] |
| **offset** | **int?** | Number of items to skip. | [optional] [default to 0] |
| **sortBy** | **string?** | Sort field. Provider-dependent; the native provider supports &#x60;updated_at&#x60;, &#x60;created_at&#x60;, &#x60;title&#x60;.  | [optional] [default to &quot;updated_at&quot;] |
| **sortOrder** | **string?** |  | [optional] [default to desc] |

### Return type

[**NoteListEnvelope**](NoteListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Fan-out envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Resolver or fan-out failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="moveblock"></a>
# **MoveBlock**
> SuccessFlag MoveBlock (string id, MoveBlockRequest moveBlockRequest, string? accountId = null, string? xWorkspaceID = null)

Reparent or reorder a block.

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
    public class MoveBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Block id.
            var moveBlockRequest = new MoveBlockRequest(); // MoveBlockRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Reparent or reorder a block.
                SuccessFlag result = apiInstance.MoveBlock(id, moveBlockRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.MoveBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the MoveBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Reparent or reorder a block.
    ApiResponse<SuccessFlag> response = apiInstance.MoveBlockWithHttpInfo(id, moveBlockRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.MoveBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Block id. |  |
| **moveBlockRequest** | [**MoveBlockRequest**](MoveBlockRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Block not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="rotatenotesharetoken"></a>
# **RotateNoteShareToken**
> ShareSettings RotateNoteShareToken (string id, string? accountId = null, string? xWorkspaceID = null)

Rotate the share token, invalidating any outstanding URLs.

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
    public class RotateNoteShareTokenExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Rotate the share token, invalidating any outstanding URLs.
                ShareSettings result = apiInstance.RotateNoteShareToken(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.RotateNoteShareToken: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RotateNoteShareTokenWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Rotate the share token, invalidating any outstanding URLs.
    ApiResponse<ShareSettings> response = apiInstance.RotateNoteShareTokenWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.RotateNoteShareTokenWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | New share settings (with the new token + URL). |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the note owner. |  -  |
| **404** | Note not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateblock"></a>
# **UpdateBlock**
> Block UpdateBlock (string id, UpdateBlockRequest updateBlockRequest, string? accountId = null, string? xWorkspaceID = null)

Update a block (partial).

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
    public class UpdateBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Block id.
            var updateBlockRequest = new UpdateBlockRequest(); // UpdateBlockRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Update a block (partial).
                Block result = apiInstance.UpdateBlock(id, updateBlockRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.UpdateBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a block (partial).
    ApiResponse<Block> response = apiInstance.UpdateBlockWithHttpInfo(id, updateBlockRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.UpdateBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Block id. |  |
| **updateBlockRequest** | [**UpdateBlockRequest**](UpdateBlockRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Block**](Block.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated block. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Block not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatenote"></a>
# **UpdateNote**
> Note UpdateNote (string id, UpdateNoteRequest updateNoteRequest, string? accountId = null, string? xWorkspaceID = null)

Update a note (partial).

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
    public class UpdateNoteExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var updateNoteRequest = new UpdateNoteRequest(); // UpdateNoteRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Update a note (partial).
                Note result = apiInstance.UpdateNote(id, updateNoteRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.UpdateNote: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateNoteWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a note (partial).
    ApiResponse<Note> response = apiInstance.UpdateNoteWithHttpInfo(id, updateNoteRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.UpdateNoteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **updateNoteRequest** | [**UpdateNoteRequest**](UpdateNoteRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Note**](Note.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated note. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Note not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatenotecomment"></a>
# **UpdateNoteComment**
> CommentMutationResponse UpdateNoteComment (string id, string commentId, UpdateCommentRequest updateCommentRequest, string? accountId = null, string? xWorkspaceID = null)

Edit a comment.

Only the comment author can edit. The note owner can delete via `DELETE` but cannot rewrite. 

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
    public class UpdateNoteCommentExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Note id.
            var commentId = "commentId_example";  // string | Comment id.
            var updateCommentRequest = new UpdateCommentRequest(); // UpdateCommentRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Edit a comment.
                CommentMutationResponse result = apiInstance.UpdateNoteComment(id, commentId, updateCommentRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.UpdateNoteComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateNoteCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Edit a comment.
    ApiResponse<CommentMutationResponse> response = apiInstance.UpdateNoteCommentWithHttpInfo(id, commentId, updateCommentRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.UpdateNoteCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Note id. |  |
| **commentId** | **string** | Comment id. |  |
| **updateCommentRequest** | [**UpdateCommentRequest**](UpdateCommentRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**CommentMutationResponse**](CommentMutationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment updated. |  -  |
| **400** | Missing body or comment id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the comment author. |  -  |
| **404** | Comment not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacecreatenote"></a>
# **WorkspaceCreateNote**
> Dictionary&lt;string, Object&gt; WorkspaceCreateNote (string org, string workspace, Dictionary<string, Object> requestBody)



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
    public class WorkspaceCreateNoteExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceCreateNote(org, workspace, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceCreateNote: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceCreateNoteWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceCreateNoteWithHttpInfo(org, workspace, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceCreateNoteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
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
| **201** | Created |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacecreatenoteblock"></a>
# **WorkspaceCreateNoteBlock**
> Dictionary&lt;string, Object&gt; WorkspaceCreateNoteBlock (string org, string workspace, string id, Dictionary<string, Object> requestBody)



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
    public class WorkspaceCreateNoteBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceCreateNoteBlock(org, workspace, id, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceCreateNoteBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceCreateNoteBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceCreateNoteBlockWithHttpInfo(org, workspace, id, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceCreateNoteBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **id** | **string** |  |  |
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
| **201** | Created |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacedeletenote"></a>
# **WorkspaceDeleteNote**
> void WorkspaceDeleteNote (string org, string workspace, string id)



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
    public class WorkspaceDeleteNoteExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                apiInstance.WorkspaceDeleteNote(org, workspace, id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceDeleteNote: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceDeleteNoteWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    apiInstance.WorkspaceDeleteNoteWithHttpInfo(org, workspace, id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceDeleteNoteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **id** | **string** |  |  |

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
| **204** | Deleted |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacedeletenoteblock"></a>
# **WorkspaceDeleteNoteBlock**
> void WorkspaceDeleteNoteBlock (string org, string workspace, string id)



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
    public class WorkspaceDeleteNoteBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                apiInstance.WorkspaceDeleteNoteBlock(org, workspace, id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceDeleteNoteBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceDeleteNoteBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    apiInstance.WorkspaceDeleteNoteBlockWithHttpInfo(org, workspace, id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceDeleteNoteBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **id** | **string** |  |  |

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
| **204** | Deleted |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacegetnote"></a>
# **WorkspaceGetNote**
> Dictionary&lt;string, Object&gt; WorkspaceGetNote (string org, string workspace, string id)



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
    public class WorkspaceGetNoteExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceGetNote(org, workspace, id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceGetNote: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceGetNoteWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceGetNoteWithHttpInfo(org, workspace, id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceGetNoteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **id** | **string** |  |  |

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
| **200** | Note |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacegetnoteblock"></a>
# **WorkspaceGetNoteBlock**
> Dictionary&lt;string, Object&gt; WorkspaceGetNoteBlock (string org, string workspace, string id)



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
    public class WorkspaceGetNoteBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceGetNoteBlock(org, workspace, id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceGetNoteBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceGetNoteBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceGetNoteBlockWithHttpInfo(org, workspace, id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceGetNoteBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **id** | **string** |  |  |

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
| **200** | Block |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacelistnoteblocks"></a>
# **WorkspaceListNoteBlocks**
> Dictionary&lt;string, Object&gt; WorkspaceListNoteBlocks (string org, string workspace, string id)



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
    public class WorkspaceListNoteBlocksExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceListNoteBlocks(org, workspace, id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceListNoteBlocks: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceListNoteBlocksWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceListNoteBlocksWithHttpInfo(org, workspace, id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceListNoteBlocksWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **id** | **string** |  |  |

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
| **200** | Blocks |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacelistnotes"></a>
# **WorkspaceListNotes**
> Dictionary&lt;string, Object&gt; WorkspaceListNotes (string org, string workspace)



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
    public class WorkspaceListNotesExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceListNotes(org, workspace);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceListNotes: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceListNotesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceListNotesWithHttpInfo(org, workspace);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceListNotesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |

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
| **200** | Notes |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacemovenoteblock"></a>
# **WorkspaceMoveNoteBlock**
> Dictionary&lt;string, Object&gt; WorkspaceMoveNoteBlock (string org, string workspace, string id, Dictionary<string, Object> requestBody)



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
    public class WorkspaceMoveNoteBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceMoveNoteBlock(org, workspace, id, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceMoveNoteBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceMoveNoteBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceMoveNoteBlockWithHttpInfo(org, workspace, id, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceMoveNoteBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **id** | **string** |  |  |
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
| **200** | Moved |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspaceupdatenote"></a>
# **WorkspaceUpdateNote**
> Dictionary&lt;string, Object&gt; WorkspaceUpdateNote (string org, string workspace, string id, Dictionary<string, Object> requestBody)



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
    public class WorkspaceUpdateNoteExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceUpdateNote(org, workspace, id, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceUpdateNote: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceUpdateNoteWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceUpdateNoteWithHttpInfo(org, workspace, id, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceUpdateNoteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **id** | **string** |  |  |
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
| **200** | Updated |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspaceupdatenoteblock"></a>
# **WorkspaceUpdateNoteBlock**
> Dictionary&lt;string, Object&gt; WorkspaceUpdateNoteBlock (string org, string workspace, string id, Dictionary<string, Object> requestBody)



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
    public class WorkspaceUpdateNoteBlockExample
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
            var apiInstance = new NotesApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceUpdateNoteBlock(org, workspace, id, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotesApi.WorkspaceUpdateNoteBlock: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceUpdateNoteBlockWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceUpdateNoteBlockWithHttpInfo(org, workspace, id, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotesApi.WorkspaceUpdateNoteBlockWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **id** | **string** |  |  |
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
| **200** | Updated |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

