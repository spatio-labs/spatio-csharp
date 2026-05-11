# Spatio.Sdk.Api.ConversationsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateConversation**](ConversationsApi.md#createconversation) | **POST** /v1/conversations | Persist a new LLM conversation. |
| [**DeleteConversation**](ConversationsApi.md#deleteconversation) | **DELETE** /v1/conversations/{id} | Soft-delete a conversation. |
| [**GetConversation**](ConversationsApi.md#getconversation) | **GET** /v1/conversations/{id} | Fetch one conversation. |
| [**GetLatestConversationForContext**](ConversationsApi.md#getlatestconversationforcontext) | **GET** /v1/conversations/latest | Fetch the most recently active conversation for a given context tag. |
| [**ListConversationMessages**](ConversationsApi.md#listconversationmessages) | **GET** /v1/conversations/{id}/messages | List messages in a conversation. |
| [**ListConversations**](ConversationsApi.md#listconversations) | **GET** /v1/conversations | List the caller&#39;s persisted LLM conversations. |
| [**SaveConversationMessage**](ConversationsApi.md#saveconversationmessage) | **POST** /v1/conversations/{id}/messages | Append a message to a conversation. |
| [**UpdateConversation**](ConversationsApi.md#updateconversation) | **PATCH** /v1/conversations/{id} | Update conversation metadata (title, context, cwd, session_id, pinned). |
| [**UpdateConversationMessageMetadata**](ConversationsApi.md#updateconversationmessagemetadata) | **PATCH** /v1/conversations/{id}/messages | Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message).  |

<a id="createconversation"></a>
# **CreateConversation**
> Conversation CreateConversation (CreateConversationRequest? createConversationRequest = null)

Persist a new LLM conversation.

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
    public class CreateConversationExample
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
            var apiInstance = new ConversationsApi(httpClient, config, httpClientHandler);
            var createConversationRequest = new CreateConversationRequest?(); // CreateConversationRequest? |  (optional) 

            try
            {
                // Persist a new LLM conversation.
                Conversation result = apiInstance.CreateConversation(createConversationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConversationsApi.CreateConversation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateConversationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Persist a new LLM conversation.
    ApiResponse<Conversation> response = apiInstance.CreateConversationWithHttpInfo(createConversationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConversationsApi.CreateConversationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createConversationRequest** | [**CreateConversationRequest?**](CreateConversationRequest?.md) |  | [optional]  |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created conversation. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteconversation"></a>
# **DeleteConversation**
> void DeleteConversation (string id)

Soft-delete a conversation.

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
    public class DeleteConversationExample
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
            var apiInstance = new ConversationsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // Soft-delete a conversation.
                apiInstance.DeleteConversation(id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConversationsApi.DeleteConversation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteConversationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Soft-delete a conversation.
    apiInstance.DeleteConversationWithHttpInfo(id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConversationsApi.DeleteConversationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
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
| **204** | Deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getconversation"></a>
# **GetConversation**
> Conversation GetConversation (string id)

Fetch one conversation.

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
    public class GetConversationExample
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
            var apiInstance = new ConversationsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // Fetch one conversation.
                Conversation result = apiInstance.GetConversation(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConversationsApi.GetConversation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetConversationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch one conversation.
    ApiResponse<Conversation> response = apiInstance.GetConversationWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConversationsApi.GetConversationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Conversation. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Conversation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getlatestconversationforcontext"></a>
# **GetLatestConversationForContext**
> Conversation GetLatestConversationForContext (string context)

Fetch the most recently active conversation for a given context tag.

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
    public class GetLatestConversationForContextExample
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
            var apiInstance = new ConversationsApi(httpClient, config, httpClientHandler);
            var context = "context_example";  // string | 

            try
            {
                // Fetch the most recently active conversation for a given context tag.
                Conversation result = apiInstance.GetLatestConversationForContext(context);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConversationsApi.GetLatestConversationForContext: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetLatestConversationForContextWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch the most recently active conversation for a given context tag.
    ApiResponse<Conversation> response = apiInstance.GetLatestConversationForContextWithHttpInfo(context);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConversationsApi.GetLatestConversationForContextWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **context** | **string** |  |  |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The matching conversation, if any. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | No conversation found for that context. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listconversationmessages"></a>
# **ListConversationMessages**
> List&lt;ConversationMessage&gt; ListConversationMessages (string id, int? limit = null, string? before = null)

List messages in a conversation.

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
    public class ListConversationMessagesExample
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
            var apiInstance = new ConversationsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 
            var limit = 56;  // int? |  (optional) 
            var before = "before_example";  // string? |  (optional) 

            try
            {
                // List messages in a conversation.
                List<ConversationMessage> result = apiInstance.ListConversationMessages(id, limit, before);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConversationsApi.ListConversationMessages: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListConversationMessagesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List messages in a conversation.
    ApiResponse<List<ConversationMessage>> response = apiInstance.ListConversationMessagesWithHttpInfo(id, limit, before);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConversationsApi.ListConversationMessagesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |
| **limit** | **int?** |  | [optional]  |
| **before** | **string?** |  | [optional]  |

### Return type

[**List&lt;ConversationMessage&gt;**](ConversationMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message list (bare array). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listconversations"></a>
# **ListConversations**
> List&lt;Conversation&gt; ListConversations (string? context = null, int? limit = null)

List the caller's persisted LLM conversations.

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
    public class ListConversationsExample
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
            var apiInstance = new ConversationsApi(httpClient, config, httpClientHandler);
            var context = "context_example";  // string? |  (optional) 
            var limit = 56;  // int? |  (optional) 

            try
            {
                // List the caller's persisted LLM conversations.
                List<Conversation> result = apiInstance.ListConversations(context, limit);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConversationsApi.ListConversations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListConversationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List the caller's persisted LLM conversations.
    ApiResponse<List<Conversation>> response = apiInstance.ListConversationsWithHttpInfo(context, limit);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConversationsApi.ListConversationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **context** | **string?** |  | [optional]  |
| **limit** | **int?** |  | [optional]  |

### Return type

[**List&lt;Conversation&gt;**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Conversation list (bare array — no envelope). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="saveconversationmessage"></a>
# **SaveConversationMessage**
> ConversationMessage SaveConversationMessage (string id, SaveMessageRequest saveMessageRequest)

Append a message to a conversation.

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
    public class SaveConversationMessageExample
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
            var apiInstance = new ConversationsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 
            var saveMessageRequest = new SaveMessageRequest(); // SaveMessageRequest | 

            try
            {
                // Append a message to a conversation.
                ConversationMessage result = apiInstance.SaveConversationMessage(id, saveMessageRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConversationsApi.SaveConversationMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SaveConversationMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Append a message to a conversation.
    ApiResponse<ConversationMessage> response = apiInstance.SaveConversationMessageWithHttpInfo(id, saveMessageRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConversationsApi.SaveConversationMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |
| **saveMessageRequest** | [**SaveMessageRequest**](SaveMessageRequest.md) |  |  |

### Return type

[**ConversationMessage**](ConversationMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Saved message. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateconversation"></a>
# **UpdateConversation**
> Conversation UpdateConversation (string id, UpdateConversationRequest updateConversationRequest)

Update conversation metadata (title, context, cwd, session_id, pinned).

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
    public class UpdateConversationExample
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
            var apiInstance = new ConversationsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 
            var updateConversationRequest = new UpdateConversationRequest(); // UpdateConversationRequest | 

            try
            {
                // Update conversation metadata (title, context, cwd, session_id, pinned).
                Conversation result = apiInstance.UpdateConversation(id, updateConversationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConversationsApi.UpdateConversation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateConversationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update conversation metadata (title, context, cwd, session_id, pinned).
    ApiResponse<Conversation> response = apiInstance.UpdateConversationWithHttpInfo(id, updateConversationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConversationsApi.UpdateConversationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |
| **updateConversationRequest** | [**UpdateConversationRequest**](UpdateConversationRequest.md) |  |  |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated conversation. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateconversationmessagemetadata"></a>
# **UpdateConversationMessageMetadata**
> ConversationMessage UpdateConversationMessageMetadata (string id, UpdateMessageMetadataRequest updateMessageMetadataRequest)

Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message). 

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
    public class UpdateConversationMessageMetadataExample
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
            var apiInstance = new ConversationsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 
            var updateMessageMetadataRequest = new UpdateMessageMetadataRequest(); // UpdateMessageMetadataRequest | 

            try
            {
                // Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message). 
                ConversationMessage result = apiInstance.UpdateConversationMessageMetadata(id, updateMessageMetadataRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConversationsApi.UpdateConversationMessageMetadata: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateConversationMessageMetadataWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message). 
    ApiResponse<ConversationMessage> response = apiInstance.UpdateConversationMessageMetadataWithHttpInfo(id, updateMessageMetadataRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConversationsApi.UpdateConversationMessageMetadataWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |
| **updateMessageMetadataRequest** | [**UpdateMessageMetadataRequest**](UpdateMessageMetadataRequest.md) |  |  |

### Return type

[**ConversationMessage**](ConversationMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated message. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

