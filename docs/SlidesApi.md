# Spatio.Sdk.Api.SlidesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreatePresentation**](SlidesApi.md#createpresentation) | **POST** /v1/slides | Create a presentation. |
| [**CreateSlide**](SlidesApi.md#createslide) | **POST** /v1/slides/{id}/slides | Insert a slide. |
| [**CreateSlideElement**](SlidesApi.md#createslideelement) | **POST** /v1/slides/{id}/slides/{slideId}/elements | Add a canvas element (text/shape/image) to a slide. |
| [**DeletePresentation**](SlidesApi.md#deletepresentation) | **DELETE** /v1/slides/{id} | Delete a presentation. |
| [**DeleteSlide**](SlidesApi.md#deleteslide) | **DELETE** /v1/slides/{id}/slides/{slideId} | Delete a slide. |
| [**DeleteSlideElement**](SlidesApi.md#deleteslideelement) | **DELETE** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Delete a slide element. |
| [**DisablePresentationShare**](SlidesApi.md#disablepresentationshare) | **DELETE** /v1/slides/{id}/share | Disable public sharing. |
| [**EnablePresentationShare**](SlidesApi.md#enablepresentationshare) | **POST** /v1/slides/{id}/share | Enable (or update password on) public sharing. |
| [**ExportPresentationPdf**](SlidesApi.md#exportpresentationpdf) | **POST** /v1/slides/{id}/export/pdf | Render the presentation as a PDF. |
| [**ExportPresentationPptx**](SlidesApi.md#exportpresentationpptx) | **POST** /v1/slides/{id}/export/pptx | Render the presentation as a PowerPoint (.pptx) file. |
| [**GetPresentation**](SlidesApi.md#getpresentation) | **GET** /v1/slides/{id} | Fetch one presentation. |
| [**GetPresentationShareSettings**](SlidesApi.md#getpresentationsharesettings) | **GET** /v1/slides/{id}/share | Fetch share settings for a presentation. |
| [**GetPublicPresentation**](SlidesApi.md#getpublicpresentation) | **GET** /public/slides/{token} | Fetch a publicly shared presentation. |
| [**GetSlide**](SlidesApi.md#getslide) | **GET** /v1/slides/{id}/slides/{slideId} | Fetch one slide. |
| [**GetSlideElement**](SlidesApi.md#getslideelement) | **GET** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Fetch one slide element. |
| [**ListPresentations**](SlidesApi.md#listpresentations) | **GET** /v1/slides | List presentations across connected accounts. |
| [**ListSlideElements**](SlidesApi.md#listslideelements) | **GET** /v1/slides/{id}/slides/{slideId}/elements | List the canvas elements on a slide. |
| [**ListSlidesInPresentation**](SlidesApi.md#listslidesinpresentation) | **GET** /v1/slides/{id}/slides | List slides in a presentation. |
| [**RotatePresentationShareToken**](SlidesApi.md#rotatepresentationsharetoken) | **POST** /v1/slides/{id}/share/rotate | Rotate the share token, invalidating outstanding URLs. |
| [**UpdatePresentation**](SlidesApi.md#updatepresentation) | **PATCH** /v1/slides/{id} | Update presentation metadata (partial). |
| [**UpdateSlide**](SlidesApi.md#updateslide) | **PATCH** /v1/slides/{id}/slides/{slideId} | Update a slide (partial). |
| [**UpdateSlideElement**](SlidesApi.md#updateslideelement) | **PATCH** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Update a slide element (partial). |

<a id="createpresentation"></a>
# **CreatePresentation**
> Presentation CreatePresentation (CreatePresentationRequest createPresentationRequest, string? accountId = null, string? provider = null, string? xWorkspaceID = null)

Create a presentation.

Creates a new deck under the target account. Target resolution mirrors `POST /v1/notes` and `/v1/sheets`: body `accountId` → `?accountId=` → body `provider` → `?provider=` → caller's single connected account (errors with `ambiguous_account` otherwise). The new deck is auto-seeded with one blank slide so the renderer has something to display immediately. 

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
    public class CreatePresentationExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var createPresentationRequest = new CreatePresentationRequest(); // CreatePresentationRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var provider = "provider_example";  // string? | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Create a presentation.
                Presentation result = apiInstance.CreatePresentation(createPresentationRequest, accountId, provider, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.CreatePresentation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreatePresentationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a presentation.
    ApiResponse<Presentation> response = apiInstance.CreatePresentationWithHttpInfo(createPresentationRequest, accountId, provider, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.CreatePresentationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createPresentationRequest** | [**CreatePresentationRequest**](CreatePresentationRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **provider** | **string?** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Presentation**](Presentation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Presentation created. |  -  |
| **400** | Invalid body, ambiguous account (&#x60;code: ambiguous_account&#x60;), or no slides provider connected (&#x60;code: no_slides_provider&#x60;).  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createslide"></a>
# **CreateSlide**
> Slide CreateSlide (string id, CreateSlideRequest createSlideRequest, string? accountId = null, string? xWorkspaceID = null)

Insert a slide.

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
    public class CreateSlideExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var createSlideRequest = new CreateSlideRequest(); // CreateSlideRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Insert a slide.
                Slide result = apiInstance.CreateSlide(id, createSlideRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.CreateSlide: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateSlideWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Insert a slide.
    ApiResponse<Slide> response = apiInstance.CreateSlideWithHttpInfo(id, createSlideRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.CreateSlideWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **createSlideRequest** | [**CreateSlideRequest**](CreateSlideRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Slide**](Slide.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Slide created. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createslideelement"></a>
# **CreateSlideElement**
> SlideElement CreateSlideElement (string id, string slideId, CreateSlideElementRequest createSlideElementRequest, string? accountId = null, string? xWorkspaceID = null)

Add a canvas element (text/shape/image) to a slide.

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
    public class CreateSlideElementExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var slideId = "slideId_example";  // string | Slide id within the presentation.
            var createSlideElementRequest = new CreateSlideElementRequest(); // CreateSlideElementRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Add a canvas element (text/shape/image) to a slide.
                SlideElement result = apiInstance.CreateSlideElement(id, slideId, createSlideElementRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.CreateSlideElement: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateSlideElementWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Add a canvas element (text/shape/image) to a slide.
    ApiResponse<SlideElement> response = apiInstance.CreateSlideElementWithHttpInfo(id, slideId, createSlideElementRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.CreateSlideElementWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **slideId** | **string** | Slide id within the presentation. |  |
| **createSlideElementRequest** | [**CreateSlideElementRequest**](CreateSlideElementRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**SlideElement**](SlideElement.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Element created. |  -  |
| **400** | Invalid body, missing elementType, or missing path id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletepresentation"></a>
# **DeletePresentation**
> SuccessFlag DeletePresentation (string id, string? accountId = null, string? xWorkspaceID = null)

Delete a presentation.

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
    public class DeletePresentationExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Delete a presentation.
                SuccessFlag result = apiInstance.DeletePresentation(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.DeletePresentation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeletePresentationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a presentation.
    ApiResponse<SuccessFlag> response = apiInstance.DeletePresentationWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.DeletePresentationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
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
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteslide"></a>
# **DeleteSlide**
> SuccessFlag DeleteSlide (string id, string slideId, string? accountId = null, string? xWorkspaceID = null)

Delete a slide.

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
    public class DeleteSlideExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var slideId = "slideId_example";  // string | Slide id within the presentation.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Delete a slide.
                SuccessFlag result = apiInstance.DeleteSlide(id, slideId, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.DeleteSlide: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteSlideWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a slide.
    ApiResponse<SuccessFlag> response = apiInstance.DeleteSlideWithHttpInfo(id, slideId, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.DeleteSlideWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **slideId** | **string** | Slide id within the presentation. |  |
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
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteslideelement"></a>
# **DeleteSlideElement**
> SuccessFlag DeleteSlideElement (string id, string slideId, string elementId, string? accountId = null, string? xWorkspaceID = null)

Delete a slide element.

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
    public class DeleteSlideElementExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var slideId = "slideId_example";  // string | Slide id within the presentation.
            var elementId = "elementId_example";  // string | Slide-element id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Delete a slide element.
                SuccessFlag result = apiInstance.DeleteSlideElement(id, slideId, elementId, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.DeleteSlideElement: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteSlideElementWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a slide element.
    ApiResponse<SuccessFlag> response = apiInstance.DeleteSlideElementWithHttpInfo(id, slideId, elementId, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.DeleteSlideElementWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **slideId** | **string** | Slide id within the presentation. |  |
| **elementId** | **string** | Slide-element id. |  |
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
| **404** | Element not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="disablepresentationshare"></a>
# **DisablePresentationShare**
> void DisablePresentationShare (string id, string? accountId = null, string? xWorkspaceID = null)

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
    public class DisablePresentationShareExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Disable public sharing.
                apiInstance.DisablePresentationShare(id, accountId, xWorkspaceID);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.DisablePresentationShare: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DisablePresentationShareWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Disable public sharing.
    apiInstance.DisablePresentationShareWithHttpInfo(id, accountId, xWorkspaceID);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.DisablePresentationShareWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
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
| **403** | Caller is not the deck owner. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="enablepresentationshare"></a>
# **EnablePresentationShare**
> ShareSettings EnablePresentationShare (string id, string? accountId = null, string? xWorkspaceID = null, EnableShareRequest? enableShareRequest = null)

Enable (or update password on) public sharing.

Owner-only. With `setPassword: false` (or empty body), flips the deck public without changing the password. With `setPassword: true`, applies `password` (empty clears). 

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
    public class EnablePresentationShareExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 
            var enableShareRequest = new EnableShareRequest?(); // EnableShareRequest? |  (optional) 

            try
            {
                // Enable (or update password on) public sharing.
                ShareSettings result = apiInstance.EnablePresentationShare(id, accountId, xWorkspaceID, enableShareRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.EnablePresentationShare: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the EnablePresentationShareWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Enable (or update password on) public sharing.
    ApiResponse<ShareSettings> response = apiInstance.EnablePresentationShareWithHttpInfo(id, accountId, xWorkspaceID, enableShareRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.EnablePresentationShareWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
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
| **403** | Caller is not the deck owner. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="exportpresentationpdf"></a>
# **ExportPresentationPdf**
> FileParameter ExportPresentationPdf (string id, string? accountId = null, string? xWorkspaceID = null, string? storage = null, string? filename = null, ExportPDFRequest? exportPDFRequest = null)

Render the presentation as a PDF.

Proxies to the Spatio export sidecar (Playwright). Two response modes selected via `?storage=`:    - `stream` (default) — response body is the PDF binary     (`application/pdf`).   - `r2` — uploads the rendered PDF to R2 storage and returns     a JSON envelope with a 24-hour signed URL.  Returns `503 Service Unavailable` when the export sidecar is not configured (dev fallback to the client-side exporter). 

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
    public class ExportPresentationPdfExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 
            var storage = "stream";  // string? |  (optional)  (default to stream)
            var filename = "filename_example";  // string? | Sanitized base name for the downloaded PDF. (optional) 
            var exportPDFRequest = new ExportPDFRequest?(); // ExportPDFRequest? |  (optional) 

            try
            {
                // Render the presentation as a PDF.
                FileParameter result = apiInstance.ExportPresentationPdf(id, accountId, xWorkspaceID, storage, filename, exportPDFRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.ExportPresentationPdf: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ExportPresentationPdfWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Render the presentation as a PDF.
    ApiResponse<FileParameter> response = apiInstance.ExportPresentationPdfWithHttpInfo(id, accountId, xWorkspaceID, storage, filename, exportPDFRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.ExportPresentationPdfWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |
| **storage** | **string?** |  | [optional] [default to stream] |
| **filename** | **string?** | Sanitized base name for the downloaded PDF. | [optional]  |
| **exportPDFRequest** | [**ExportPDFRequest?**](ExportPDFRequest?.md) |  | [optional]  |

### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/pdf, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Either the PDF binary (when &#x60;?storage&#x3D;stream&#x60;) or a JSON envelope with a signed URL (when &#x60;?storage&#x3D;r2&#x60;).  |  -  |
| **400** | Missing id, presentation has no slides, or invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **502** | Export sidecar unreachable or upstream R2 failure. |  -  |
| **503** | Export sidecar not configured. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="exportpresentationpptx"></a>
# **ExportPresentationPptx**
> FileParameter ExportPresentationPptx (string id, string? accountId = null, string? xWorkspaceID = null, string? storage = null, string? filename = null, ExportPDFRequest? exportPDFRequest = null)

Render the presentation as a PowerPoint (.pptx) file.

Proxies to the Spatio export sidecar (Playwright + pptxgenjs). Each slide is screenshotted at 2× device-pixel ratio and wrapped into a PowerPoint .pptx as a full-bleed image. Visual fidelity is preserved exactly — what renders in Spatio renders identically in PowerPoint, Keynote, Google Slides — at the cost of in-PowerPoint editability of slide content. Users edit slide content back in Spatio (the source of truth), not inside PowerPoint.  Two response modes selected via `?storage=`:    - `stream` (default) — response body is the PPTX binary     (`application/vnd.openxmlformats-officedocument.presentationml.presentation`).   - `r2` — uploads the rendered PPTX to R2 storage and returns     a JSON envelope with a 24-hour signed URL.  Returns `503 Service Unavailable` when the export sidecar is not configured. 

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
    public class ExportPresentationPptxExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 
            var storage = "stream";  // string? |  (optional)  (default to stream)
            var filename = "filename_example";  // string? | Sanitized base name for the downloaded PPTX. (optional) 
            var exportPDFRequest = new ExportPDFRequest?(); // ExportPDFRequest? |  (optional) 

            try
            {
                // Render the presentation as a PowerPoint (.pptx) file.
                FileParameter result = apiInstance.ExportPresentationPptx(id, accountId, xWorkspaceID, storage, filename, exportPDFRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.ExportPresentationPptx: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ExportPresentationPptxWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Render the presentation as a PowerPoint (.pptx) file.
    ApiResponse<FileParameter> response = apiInstance.ExportPresentationPptxWithHttpInfo(id, accountId, xWorkspaceID, storage, filename, exportPDFRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.ExportPresentationPptxWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |
| **storage** | **string?** |  | [optional] [default to stream] |
| **filename** | **string?** | Sanitized base name for the downloaded PPTX. | [optional]  |
| **exportPDFRequest** | [**ExportPDFRequest?**](ExportPDFRequest?.md) |  | [optional]  |

### Return type

[**FileParameter**](FileParameter.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.openxmlformats-officedocument.presentationml.presentation, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Either the PPTX binary (when &#x60;?storage&#x3D;stream&#x60;) or a JSON envelope with a signed URL (when &#x60;?storage&#x3D;r2&#x60;).  |  -  |
| **400** | Missing id, presentation has no slides, or invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **502** | Export sidecar unreachable or upstream R2 failure. |  -  |
| **503** | Export sidecar not configured. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getpresentation"></a>
# **GetPresentation**
> Presentation GetPresentation (string id, string? accountId = null, string? xWorkspaceID = null)

Fetch one presentation.

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
    public class GetPresentationExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Fetch one presentation.
                Presentation result = apiInstance.GetPresentation(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.GetPresentation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPresentationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch one presentation.
    ApiResponse<Presentation> response = apiInstance.GetPresentationWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.GetPresentationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Presentation**](Presentation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The presentation. |  -  |
| **400** | Missing id or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getpresentationsharesettings"></a>
# **GetPresentationShareSettings**
> ShareSettings GetPresentationShareSettings (string id, string? accountId = null, string? xWorkspaceID = null)

Fetch share settings for a presentation.

Owner-only. Mirror of `GET /v1/notes/{id}/share` — same shape, same fields. Returns the current public-share configuration, including the share token and computed public viewer URL when the deck is currently public. 

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
    public class GetPresentationShareSettingsExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Fetch share settings for a presentation.
                ShareSettings result = apiInstance.GetPresentationShareSettings(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.GetPresentationShareSettings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPresentationShareSettingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch share settings for a presentation.
    ApiResponse<ShareSettings> response = apiInstance.GetPresentationShareSettingsWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.GetPresentationShareSettingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
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
| **403** | Caller is not the deck owner. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getpublicpresentation"></a>
# **GetPublicPresentation**
> Dictionary&lt;string, Object&gt; GetPublicPresentation (string token, string? password = null)

Fetch a publicly shared presentation.

Unauthenticated. Mirror of `GET /public/notes/{token}`. The share token is the credential. For password-protected decks the password is supplied via `?password=`; the response distinguishes \"no password supplied\" from \"wrong password\" so the viewer can render the right prompt. Unknown tokens and disabled-share decks both return `404` to prevent enumeration. 

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
    public class GetPublicPresentationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.spatio.app";
            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var token = "token_example";  // string | Opaque public-share token.
            var password = "password_example";  // string? | Optional viewer password. (optional) 

            try
            {
                // Fetch a publicly shared presentation.
                Dictionary<string, Object> result = apiInstance.GetPublicPresentation(token, password);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.GetPublicPresentation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPublicPresentationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch a publicly shared presentation.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.GetPublicPresentationWithHttpInfo(token, password);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.GetPublicPresentationWithHttpInfo: " + e.Message);
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
| **200** | Read-only snapshot of the shared presentation. |  -  |
| **400** | Missing token. |  -  |
| **401** | Password-protected deck. &#x60;requiresPassword: true&#x60; always set; &#x60;invalidPassword: true&#x60; only when a password was supplied and rejected.  |  -  |
| **404** | Token unknown or sharing disabled. |  -  |
| **500** | Snapshot rendering failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getslide"></a>
# **GetSlide**
> Slide GetSlide (string id, string slideId, string? accountId = null, string? xWorkspaceID = null)

Fetch one slide.

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
    public class GetSlideExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var slideId = "slideId_example";  // string | Slide id within the presentation.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Fetch one slide.
                Slide result = apiInstance.GetSlide(id, slideId, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.GetSlide: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetSlideWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch one slide.
    ApiResponse<Slide> response = apiInstance.GetSlideWithHttpInfo(id, slideId, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.GetSlideWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **slideId** | **string** | Slide id within the presentation. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Slide**](Slide.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The slide. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getslideelement"></a>
# **GetSlideElement**
> SlideElement GetSlideElement (string id, string slideId, string elementId, string? accountId = null, string? xWorkspaceID = null)

Fetch one slide element.

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
    public class GetSlideElementExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var slideId = "slideId_example";  // string | Slide id within the presentation.
            var elementId = "elementId_example";  // string | Slide-element id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Fetch one slide element.
                SlideElement result = apiInstance.GetSlideElement(id, slideId, elementId, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.GetSlideElement: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetSlideElementWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch one slide element.
    ApiResponse<SlideElement> response = apiInstance.GetSlideElementWithHttpInfo(id, slideId, elementId, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.GetSlideElementWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **slideId** | **string** | Slide id within the presentation. |  |
| **elementId** | **string** | Slide-element id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**SlideElement**](SlideElement.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The element. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Element not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listpresentations"></a>
# **ListPresentations**
> PresentationListEnvelope ListPresentations (string? accountId = null, string? provider = null, string? xWorkspaceID = null, int? limit = null, int? offset = null)

List presentations across connected accounts.

Fan-out list. Returns every presentation visible to the caller across every connected slides provider. Pass `?accountId=` or `?provider=` to scope to a single source. 

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
    public class ListPresentationsExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var provider = "provider_example";  // string? | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 
            var limit = 50;  // int? |  (optional)  (default to 50)
            var offset = 0;  // int? |  (optional)  (default to 0)

            try
            {
                // List presentations across connected accounts.
                PresentationListEnvelope result = apiInstance.ListPresentations(accountId, provider, xWorkspaceID, limit, offset);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.ListPresentations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListPresentationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List presentations across connected accounts.
    ApiResponse<PresentationListEnvelope> response = apiInstance.ListPresentationsWithHttpInfo(accountId, provider, xWorkspaceID, limit, offset);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.ListPresentationsWithHttpInfo: " + e.Message);
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
| **limit** | **int?** |  | [optional] [default to 50] |
| **offset** | **int?** |  | [optional] [default to 0] |

### Return type

[**PresentationListEnvelope**](PresentationListEnvelope.md)

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

<a id="listslideelements"></a>
# **ListSlideElements**
> SlideElementList ListSlideElements (string id, string slideId, string? accountId = null, string? xWorkspaceID = null)

List the canvas elements on a slide.

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
    public class ListSlideElementsExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var slideId = "slideId_example";  // string | Slide id within the presentation.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // List the canvas elements on a slide.
                SlideElementList result = apiInstance.ListSlideElements(id, slideId, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.ListSlideElements: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListSlideElementsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List the canvas elements on a slide.
    ApiResponse<SlideElementList> response = apiInstance.ListSlideElementsWithHttpInfo(id, slideId, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.ListSlideElementsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **slideId** | **string** | Slide id within the presentation. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**SlideElementList**](SlideElementList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Slide-element list. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listslidesinpresentation"></a>
# **ListSlidesInPresentation**
> SlideList ListSlidesInPresentation (string id, string? accountId = null, string? xWorkspaceID = null)

List slides in a presentation.

Single-account list. Returns slides in the order set by their `position` field. 

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
    public class ListSlidesInPresentationExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // List slides in a presentation.
                SlideList result = apiInstance.ListSlidesInPresentation(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.ListSlidesInPresentation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListSlidesInPresentationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List slides in a presentation.
    ApiResponse<SlideList> response = apiInstance.ListSlidesInPresentationWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.ListSlidesInPresentationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**SlideList**](SlideList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Slide list. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="rotatepresentationsharetoken"></a>
# **RotatePresentationShareToken**
> ShareSettings RotatePresentationShareToken (string id, string? accountId = null, string? xWorkspaceID = null)

Rotate the share token, invalidating outstanding URLs.

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
    public class RotatePresentationShareTokenExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Rotate the share token, invalidating outstanding URLs.
                ShareSettings result = apiInstance.RotatePresentationShareToken(id, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.RotatePresentationShareToken: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RotatePresentationShareTokenWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Rotate the share token, invalidating outstanding URLs.
    ApiResponse<ShareSettings> response = apiInstance.RotatePresentationShareTokenWithHttpInfo(id, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.RotatePresentationShareTokenWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
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
| **403** | Caller is not the deck owner. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatepresentation"></a>
# **UpdatePresentation**
> Presentation UpdatePresentation (string id, UpdatePresentationRequest updatePresentationRequest, string? accountId = null, string? xWorkspaceID = null)

Update presentation metadata (partial).

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
    public class UpdatePresentationExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var updatePresentationRequest = new UpdatePresentationRequest(); // UpdatePresentationRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Update presentation metadata (partial).
                Presentation result = apiInstance.UpdatePresentation(id, updatePresentationRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.UpdatePresentation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdatePresentationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update presentation metadata (partial).
    ApiResponse<Presentation> response = apiInstance.UpdatePresentationWithHttpInfo(id, updatePresentationRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.UpdatePresentationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **updatePresentationRequest** | [**UpdatePresentationRequest**](UpdatePresentationRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Presentation**](Presentation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated presentation. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateslide"></a>
# **UpdateSlide**
> Slide UpdateSlide (string id, string slideId, UpdateSlideRequest updateSlideRequest, string? accountId = null, string? xWorkspaceID = null)

Update a slide (partial).

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
    public class UpdateSlideExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var slideId = "slideId_example";  // string | Slide id within the presentation.
            var updateSlideRequest = new UpdateSlideRequest(); // UpdateSlideRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Update a slide (partial).
                Slide result = apiInstance.UpdateSlide(id, slideId, updateSlideRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.UpdateSlide: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateSlideWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a slide (partial).
    ApiResponse<Slide> response = apiInstance.UpdateSlideWithHttpInfo(id, slideId, updateSlideRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.UpdateSlideWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **slideId** | **string** | Slide id within the presentation. |  |
| **updateSlideRequest** | [**UpdateSlideRequest**](UpdateSlideRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**Slide**](Slide.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated slide. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateslideelement"></a>
# **UpdateSlideElement**
> SlideElement UpdateSlideElement (string id, string slideId, string elementId, UpdateSlideElementRequest updateSlideElementRequest, string? accountId = null, string? xWorkspaceID = null)

Update a slide element (partial).

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
    public class UpdateSlideElementExample
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
            var apiInstance = new SlidesApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Presentation id.
            var slideId = "slideId_example";  // string | Slide id within the presentation.
            var elementId = "elementId_example";  // string | Slide-element id.
            var updateSlideElementRequest = new UpdateSlideElementRequest(); // UpdateSlideElementRequest | 
            var accountId = "accountId_example";  // string? | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional) 
            var xWorkspaceID = "xWorkspaceID_example";  // string? | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional) 

            try
            {
                // Update a slide element (partial).
                SlideElement result = apiInstance.UpdateSlideElement(id, slideId, elementId, updateSlideElementRequest, accountId, xWorkspaceID);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling SlidesApi.UpdateSlideElement: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateSlideElementWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a slide element (partial).
    ApiResponse<SlideElement> response = apiInstance.UpdateSlideElementWithHttpInfo(id, slideId, elementId, updateSlideElementRequest, accountId, xWorkspaceID);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling SlidesApi.UpdateSlideElementWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Presentation id. |  |
| **slideId** | **string** | Slide id within the presentation. |  |
| **elementId** | **string** | Slide-element id. |  |
| **updateSlideElementRequest** | [**UpdateSlideElementRequest**](UpdateSlideElementRequest.md) |  |  |
| **accountId** | **string?** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional]  |
| **xWorkspaceID** | **string?** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional]  |

### Return type

[**SlideElement**](SlideElement.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated element. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Element not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

