# Spatio.Sdk.Api.ActionsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ExecuteAction**](ActionsApi.md#executeaction) | **POST** /v1/actions/execute | Renderer-side execute alias. The canonical endpoint is &#x60;POST /v1/agent/actions/execute&#x60;; this path delegates to the same handler.  |
| [**GetCoreAction**](ActionsApi.md#getcoreaction) | **GET** /v1/actions/core/{id} | Fetch a single core action by id. |
| [**ListAvailableActions**](ActionsApi.md#listavailableactions) | **GET** /v1/actions/available | List every action the agent platform exposes. |
| [**ListCoreActions**](ActionsApi.md#listcoreactions) | **GET** /v1/actions/core | List renderer-curated \&quot;core actions\&quot; (command-palette + keybindings backing). |
| [**ListCoreActionsByPlatform**](ActionsApi.md#listcoreactionsbyplatform) | **GET** /v1/actions/core/platform/{platform} | Core actions filtered to one platform. |
| [**ListPlatformActions**](ActionsApi.md#listplatformactions) | **GET** /v1/actions/platform/{platform} | List actions tagged for a specific platform (notes, mail, ...). |

<a id="executeaction"></a>
# **ExecuteAction**
> ExecuteActionResponse ExecuteAction (ExecuteActionRequest executeActionRequest)

Renderer-side execute alias. The canonical endpoint is `POST /v1/agent/actions/execute`; this path delegates to the same handler. 

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
    public class ExecuteActionExample
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
            var apiInstance = new ActionsApi(httpClient, config, httpClientHandler);
            var executeActionRequest = new ExecuteActionRequest(); // ExecuteActionRequest | 

            try
            {
                // Renderer-side execute alias. The canonical endpoint is `POST /v1/agent/actions/execute`; this path delegates to the same handler. 
                ExecuteActionResponse result = apiInstance.ExecuteAction(executeActionRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ActionsApi.ExecuteAction: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ExecuteActionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Renderer-side execute alias. The canonical endpoint is `POST /v1/agent/actions/execute`; this path delegates to the same handler. 
    ApiResponse<ExecuteActionResponse> response = apiInstance.ExecuteActionWithHttpInfo(executeActionRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ActionsApi.ExecuteActionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **executeActionRequest** | [**ExecuteActionRequest**](ExecuteActionRequest.md) |  |  |

### Return type

[**ExecuteActionResponse**](ExecuteActionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Execution result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getcoreaction"></a>
# **GetCoreAction**
> CoreAction GetCoreAction (string id)

Fetch a single core action by id.

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
    public class GetCoreActionExample
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
            var apiInstance = new ActionsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // Fetch a single core action by id.
                CoreAction result = apiInstance.GetCoreAction(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ActionsApi.GetCoreAction: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetCoreActionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch a single core action by id.
    ApiResponse<CoreAction> response = apiInstance.GetCoreActionWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ActionsApi.GetCoreActionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |

### Return type

[**CoreAction**](CoreAction.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Core action. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listavailableactions"></a>
# **ListAvailableActions**
> List&lt;ActionDescriptor&gt; ListAvailableActions ()

List every action the agent platform exposes.

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
    public class ListAvailableActionsExample
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
            var apiInstance = new ActionsApi(httpClient, config, httpClientHandler);

            try
            {
                // List every action the agent platform exposes.
                List<ActionDescriptor> result = apiInstance.ListAvailableActions();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ActionsApi.ListAvailableActions: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListAvailableActionsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List every action the agent platform exposes.
    ApiResponse<List<ActionDescriptor>> response = apiInstance.ListAvailableActionsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ActionsApi.ListAvailableActionsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**List&lt;ActionDescriptor&gt;**](ActionDescriptor.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Action descriptors (bare array). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcoreactions"></a>
# **ListCoreActions**
> CoreActionListResponse ListCoreActions ()

List renderer-curated \"core actions\" (command-palette + keybindings backing).

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
    public class ListCoreActionsExample
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
            var apiInstance = new ActionsApi(httpClient, config, httpClientHandler);

            try
            {
                // List renderer-curated \"core actions\" (command-palette + keybindings backing).
                CoreActionListResponse result = apiInstance.ListCoreActions();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ActionsApi.ListCoreActions: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCoreActionsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List renderer-curated \"core actions\" (command-palette + keybindings backing).
    ApiResponse<CoreActionListResponse> response = apiInstance.ListCoreActionsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ActionsApi.ListCoreActionsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**CoreActionListResponse**](CoreActionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Core action envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcoreactionsbyplatform"></a>
# **ListCoreActionsByPlatform**
> CoreActionListResponse ListCoreActionsByPlatform (string platform)

Core actions filtered to one platform.

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
    public class ListCoreActionsByPlatformExample
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
            var apiInstance = new ActionsApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string | 

            try
            {
                // Core actions filtered to one platform.
                CoreActionListResponse result = apiInstance.ListCoreActionsByPlatform(platform);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ActionsApi.ListCoreActionsByPlatform: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCoreActionsByPlatformWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Core actions filtered to one platform.
    ApiResponse<CoreActionListResponse> response = apiInstance.ListCoreActionsByPlatformWithHttpInfo(platform);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ActionsApi.ListCoreActionsByPlatformWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string** |  |  |

### Return type

[**CoreActionListResponse**](CoreActionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Core action envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listplatformactions"></a>
# **ListPlatformActions**
> List&lt;ActionDescriptor&gt; ListPlatformActions (string platform)

List actions tagged for a specific platform (notes, mail, ...).

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
    public class ListPlatformActionsExample
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
            var apiInstance = new ActionsApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string | 

            try
            {
                // List actions tagged for a specific platform (notes, mail, ...).
                List<ActionDescriptor> result = apiInstance.ListPlatformActions(platform);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ActionsApi.ListPlatformActions: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListPlatformActionsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List actions tagged for a specific platform (notes, mail, ...).
    ApiResponse<List<ActionDescriptor>> response = apiInstance.ListPlatformActionsWithHttpInfo(platform);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ActionsApi.ListPlatformActionsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string** |  |  |

### Return type

[**List&lt;ActionDescriptor&gt;**](ActionDescriptor.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Action descriptors (bare array). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

