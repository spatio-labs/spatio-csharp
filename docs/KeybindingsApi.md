# Spatio.Sdk.Api.KeybindingsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteKeyBinding**](KeybindingsApi.md#deletekeybinding) | **DELETE** /v1/keybindings/{id} | Reset a binding to its platform default. |
| [**GetDefaultKeyBindings**](KeybindingsApi.md#getdefaultkeybindings) | **GET** /v1/keybindings/defaults | Platform default key bindings (no user customizations applied). |
| [**ListKeyBindings**](KeybindingsApi.md#listkeybindings) | **GET** /v1/keybindings | User&#39;s merged key bindings (defaults + customizations). |
| [**ResetAllKeyBindings**](KeybindingsApi.md#resetallkeybindings) | **POST** /v1/keybindings/reset | Reset every customization to its platform default. |
| [**UpdateKeyBinding**](KeybindingsApi.md#updatekeybinding) | **PUT** /v1/keybindings/{id} | Create or update a user key-binding customization. |
| [**ValidateKeyBinding**](KeybindingsApi.md#validatekeybinding) | **POST** /v1/keybindings/validate | Check whether a proposed binding conflicts with existing ones. |

<a id="deletekeybinding"></a>
# **DeleteKeyBinding**
> void DeleteKeyBinding (string id)

Reset a binding to its platform default.

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
    public class DeleteKeyBindingExample
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
            var apiInstance = new KeybindingsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // Reset a binding to its platform default.
                apiInstance.DeleteKeyBinding(id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling KeybindingsApi.DeleteKeyBinding: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteKeyBindingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Reset a binding to its platform default.
    apiInstance.DeleteKeyBindingWithHttpInfo(id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling KeybindingsApi.DeleteKeyBindingWithHttpInfo: " + e.Message);
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
| **204** | Reset. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getdefaultkeybindings"></a>
# **GetDefaultKeyBindings**
> KeyBindingListResponse GetDefaultKeyBindings ()

Platform default key bindings (no user customizations applied).

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
    public class GetDefaultKeyBindingsExample
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
            var apiInstance = new KeybindingsApi(httpClient, config, httpClientHandler);

            try
            {
                // Platform default key bindings (no user customizations applied).
                KeyBindingListResponse result = apiInstance.GetDefaultKeyBindings();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling KeybindingsApi.GetDefaultKeyBindings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetDefaultKeyBindingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Platform default key bindings (no user customizations applied).
    ApiResponse<KeyBindingListResponse> response = apiInstance.GetDefaultKeyBindingsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling KeybindingsApi.GetDefaultKeyBindingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**KeyBindingListResponse**](KeyBindingListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Default bindings envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listkeybindings"></a>
# **ListKeyBindings**
> KeyBindingListResponse ListKeyBindings ()

User's merged key bindings (defaults + customizations).

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
    public class ListKeyBindingsExample
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
            var apiInstance = new KeybindingsApi(httpClient, config, httpClientHandler);

            try
            {
                // User's merged key bindings (defaults + customizations).
                KeyBindingListResponse result = apiInstance.ListKeyBindings();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling KeybindingsApi.ListKeyBindings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListKeyBindingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // User's merged key bindings (defaults + customizations).
    ApiResponse<KeyBindingListResponse> response = apiInstance.ListKeyBindingsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling KeybindingsApi.ListKeyBindingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**KeyBindingListResponse**](KeyBindingListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bindings envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="resetallkeybindings"></a>
# **ResetAllKeyBindings**
> void ResetAllKeyBindings ()

Reset every customization to its platform default.

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
    public class ResetAllKeyBindingsExample
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
            var apiInstance = new KeybindingsApi(httpClient, config, httpClientHandler);

            try
            {
                // Reset every customization to its platform default.
                apiInstance.ResetAllKeyBindings();
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling KeybindingsApi.ResetAllKeyBindings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ResetAllKeyBindingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Reset every customization to its platform default.
    apiInstance.ResetAllKeyBindingsWithHttpInfo();
}
catch (ApiException e)
{
    Debug.Print("Exception when calling KeybindingsApi.ResetAllKeyBindingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
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
| **204** | Reset. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatekeybinding"></a>
# **UpdateKeyBinding**
> KeyBinding UpdateKeyBinding (string id, UpdateKeyBindingRequest updateKeyBindingRequest)

Create or update a user key-binding customization.

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
    public class UpdateKeyBindingExample
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
            var apiInstance = new KeybindingsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 
            var updateKeyBindingRequest = new UpdateKeyBindingRequest(); // UpdateKeyBindingRequest | 

            try
            {
                // Create or update a user key-binding customization.
                KeyBinding result = apiInstance.UpdateKeyBinding(id, updateKeyBindingRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling KeybindingsApi.UpdateKeyBinding: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateKeyBindingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create or update a user key-binding customization.
    ApiResponse<KeyBinding> response = apiInstance.UpdateKeyBindingWithHttpInfo(id, updateKeyBindingRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling KeybindingsApi.UpdateKeyBindingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |
| **updateKeyBindingRequest** | [**UpdateKeyBindingRequest**](UpdateKeyBindingRequest.md) |  |  |

### Return type

[**KeyBinding**](KeyBinding.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated binding. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="validatekeybinding"></a>
# **ValidateKeyBinding**
> ValidateKeyBindingResponse ValidateKeyBinding (ValidateKeyBindingRequest validateKeyBindingRequest)

Check whether a proposed binding conflicts with existing ones.

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
    public class ValidateKeyBindingExample
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
            var apiInstance = new KeybindingsApi(httpClient, config, httpClientHandler);
            var validateKeyBindingRequest = new ValidateKeyBindingRequest(); // ValidateKeyBindingRequest | 

            try
            {
                // Check whether a proposed binding conflicts with existing ones.
                ValidateKeyBindingResponse result = apiInstance.ValidateKeyBinding(validateKeyBindingRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling KeybindingsApi.ValidateKeyBinding: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ValidateKeyBindingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Check whether a proposed binding conflicts with existing ones.
    ApiResponse<ValidateKeyBindingResponse> response = apiInstance.ValidateKeyBindingWithHttpInfo(validateKeyBindingRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling KeybindingsApi.ValidateKeyBindingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **validateKeyBindingRequest** | [**ValidateKeyBindingRequest**](ValidateKeyBindingRequest.md) |  |  |

### Return type

[**ValidateKeyBindingResponse**](ValidateKeyBindingResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Validation result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

