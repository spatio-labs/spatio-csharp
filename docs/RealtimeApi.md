# Spatio.Sdk.Api.RealtimeApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**IssueCollaborationToken**](RealtimeApi.md#issuecollaborationtoken) | **POST** /v1/realtime/collaboration-token | Exchange a bearer token for a short-lived Yjs collaboration JWT. |

<a id="issuecollaborationtoken"></a>
# **IssueCollaborationToken**
> IssueCollaborationToken200Response IssueCollaborationToken (IssueCollaborationTokenRequest? issueCollaborationTokenRequest = null)

Exchange a bearer token for a short-lived Yjs collaboration JWT.

The Yjs Cloudflare Worker that powers live document collaboration (`wss://realtime-collaboration.<account>.workers.dev`) only accepts platform-signed JWTs. Third-party clients holding an OAuth access token or PAT call this endpoint to mint a 5-minute collaboration JWT they can present to the worker.  The minted JWT inherits user + workspace identity from the presenting bearer token. Optionally scope it to a single room by supplying `room` in the request body. 

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
    public class IssueCollaborationTokenExample
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
            var apiInstance = new RealtimeApi(httpClient, config, httpClientHandler);
            var issueCollaborationTokenRequest = new IssueCollaborationTokenRequest?(); // IssueCollaborationTokenRequest? |  (optional) 

            try
            {
                // Exchange a bearer token for a short-lived Yjs collaboration JWT.
                IssueCollaborationToken200Response result = apiInstance.IssueCollaborationToken(issueCollaborationTokenRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling RealtimeApi.IssueCollaborationToken: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the IssueCollaborationTokenWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Exchange a bearer token for a short-lived Yjs collaboration JWT.
    ApiResponse<IssueCollaborationToken200Response> response = apiInstance.IssueCollaborationTokenWithHttpInfo(issueCollaborationTokenRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling RealtimeApi.IssueCollaborationTokenWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **issueCollaborationTokenRequest** | [**IssueCollaborationTokenRequest?**](IssueCollaborationTokenRequest?.md) |  | [optional]  |

### Return type

[**IssueCollaborationToken200Response**](IssueCollaborationToken200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Token issued. |  -  |
| **401** | Bearer token invalid. |  -  |
| **500** | Server misconfigured (JWT_SECRET unset). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

