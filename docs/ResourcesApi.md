# Spatio.Sdk.Api.ResourcesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListResourcePermissionGrants**](ResourcesApi.md#listresourcepermissiongrants) | **GET** /v1/resources/{platform}/{resourceId}/permissions | List access grants on a resource (per-resource ACL). |
| [**RevokeResourcePermissionGrant**](ResourcesApi.md#revokeresourcepermissiongrant) | **DELETE** /v1/resources/{platform}/{resourceId}/permissions/{grantId} | Revoke an access grant. |
| [**SetResourcePermissionGrant**](ResourcesApi.md#setresourcepermissiongrant) | **POST** /v1/resources/{platform}/{resourceId}/permissions | Create or update an access grant. |

<a id="listresourcepermissiongrants"></a>
# **ListResourcePermissionGrants**
> Dictionary&lt;string, Object&gt; ListResourcePermissionGrants (string platform, string resourceId)

List access grants on a resource (per-resource ACL).

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
    public class ListResourcePermissionGrantsExample
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
            var apiInstance = new ResourcesApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string | 
            var resourceId = "resourceId_example";  // string | 

            try
            {
                // List access grants on a resource (per-resource ACL).
                Dictionary<string, Object> result = apiInstance.ListResourcePermissionGrants(platform, resourceId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ResourcesApi.ListResourcePermissionGrants: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListResourcePermissionGrantsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List access grants on a resource (per-resource ACL).
    ApiResponse<Dictionary<string, Object>> response = apiInstance.ListResourcePermissionGrantsWithHttpInfo(platform, resourceId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ResourcesApi.ListResourcePermissionGrantsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string** |  |  |
| **resourceId** | **string** |  |  |

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
| **200** | Grant envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="revokeresourcepermissiongrant"></a>
# **RevokeResourcePermissionGrant**
> void RevokeResourcePermissionGrant (string platform, string resourceId, string grantId)

Revoke an access grant.

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
    public class RevokeResourcePermissionGrantExample
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
            var apiInstance = new ResourcesApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string | 
            var resourceId = "resourceId_example";  // string | 
            var grantId = "grantId_example";  // string | 

            try
            {
                // Revoke an access grant.
                apiInstance.RevokeResourcePermissionGrant(platform, resourceId, grantId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ResourcesApi.RevokeResourcePermissionGrant: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RevokeResourcePermissionGrantWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Revoke an access grant.
    apiInstance.RevokeResourcePermissionGrantWithHttpInfo(platform, resourceId, grantId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ResourcesApi.RevokeResourcePermissionGrantWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string** |  |  |
| **resourceId** | **string** |  |  |
| **grantId** | **string** |  |  |

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
| **204** | Revoked. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="setresourcepermissiongrant"></a>
# **SetResourcePermissionGrant**
> Dictionary&lt;string, Object&gt; SetResourcePermissionGrant (string platform, string resourceId, Dictionary<string, Object> requestBody)

Create or update an access grant.

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
    public class SetResourcePermissionGrantExample
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
            var apiInstance = new ResourcesApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string | 
            var resourceId = "resourceId_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                // Create or update an access grant.
                Dictionary<string, Object> result = apiInstance.SetResourcePermissionGrant(platform, resourceId, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ResourcesApi.SetResourcePermissionGrant: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SetResourcePermissionGrantWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create or update an access grant.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.SetResourcePermissionGrantWithHttpInfo(platform, resourceId, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ResourcesApi.SetResourcePermissionGrantWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string** |  |  |
| **resourceId** | **string** |  |  |
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
| **200** | Created/updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

