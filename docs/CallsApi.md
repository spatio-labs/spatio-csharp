# Spatio.Sdk.Api.CallsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCall**](CallsApi.md#createcall) | **POST** /v1/calls | Start a new call. |
| [**CreateMeetingRoom**](CallsApi.md#createmeetingroom) | **POST** /v1/calls/rooms | Create a persistent meeting room. |
| [**DeleteCallRecording**](CallsApi.md#deletecallrecording) | **DELETE** /v1/calls/recordings/{recordingId} | Delete a recording. |
| [**EndCall**](CallsApi.md#endcall) | **POST** /v1/calls/{id}/end | End a call (host only). |
| [**GetBandwidthHistory**](CallsApi.md#getbandwidthhistory) | **GET** /v1/calls/bandwidth/history | Time-series bandwidth metrics. |
| [**GetBandwidthSummary**](CallsApi.md#getbandwidthsummary) | **GET** /v1/calls/bandwidth/summary | Aggregate bandwidth metrics. |
| [**GetCall**](CallsApi.md#getcall) | **GET** /v1/calls/{id} | Fetch a call. |
| [**GetMeetingRoom**](CallsApi.md#getmeetingroom) | **GET** /v1/calls/rooms/{id} | Fetch a meeting room. |
| [**JoinCall**](CallsApi.md#joincall) | **POST** /v1/calls/{id}/join | Join a call. |
| [**LeaveCall**](CallsApi.md#leavecall) | **POST** /v1/calls/{id}/leave | Leave a call. |
| [**ListActiveCalls**](CallsApi.md#listactivecalls) | **GET** /v1/calls | List active calls. |
| [**ListCallRecordings**](CallsApi.md#listcallrecordings) | **GET** /v1/calls/{id}/recordings | List recordings for a call. |
| [**StartCallRecording**](CallsApi.md#startcallrecording) | **POST** /v1/calls/{id}/recordings/start | Start a recording (host only). |
| [**StopCallRecording**](CallsApi.md#stopcallrecording) | **POST** /v1/calls/{id}/recordings/{recordingId}/stop | Stop an in-progress recording. |
| [**UpdateCallParticipantState**](CallsApi.md#updatecallparticipantstate) | **PATCH** /v1/calls/{id}/participant | Toggle participant audio/video/screen-share state. |
| [**WorkspaceCreateCall**](CallsApi.md#workspacecreatecall) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls |  |
| [**WorkspaceCreateMeetingRoom**](CallsApi.md#workspacecreatemeetingroom) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/rooms |  |
| [**WorkspaceDeleteCallRecording**](CallsApi.md#workspacedeletecallrecording) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/calls/recordings/{recordingId} |  |
| [**WorkspaceEndCall**](CallsApi.md#workspaceendcall) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/end |  |
| [**WorkspaceGetBandwidthHistory**](CallsApi.md#workspacegetbandwidthhistory) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/bandwidth/history |  |
| [**WorkspaceGetBandwidthSummary**](CallsApi.md#workspacegetbandwidthsummary) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/bandwidth/summary |  |
| [**WorkspaceGetCall**](CallsApi.md#workspacegetcall) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/{id} |  |
| [**WorkspaceGetMeetingRoom**](CallsApi.md#workspacegetmeetingroom) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/rooms/{id} |  |
| [**WorkspaceJoinCall**](CallsApi.md#workspacejoincall) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/join |  |
| [**WorkspaceLeaveCall**](CallsApi.md#workspaceleavecall) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/leave |  |
| [**WorkspaceListActiveCalls**](CallsApi.md#workspacelistactivecalls) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls |  |
| [**WorkspaceListCallRecordings**](CallsApi.md#workspacelistcallrecordings) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/recordings |  |
| [**WorkspaceStartCallRecording**](CallsApi.md#workspacestartcallrecording) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/recordings/start |  |
| [**WorkspaceStopCallRecording**](CallsApi.md#workspacestopcallrecording) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/recordings/{recordingId}/stop |  |
| [**WorkspaceUpdateCallParticipant**](CallsApi.md#workspaceupdatecallparticipant) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/participant |  |

<a id="createcall"></a>
# **CreateCall**
> SpatioCall CreateCall (CreateCallRequest? createCallRequest = null)

Start a new call.

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
    public class CreateCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var createCallRequest = new CreateCallRequest?(); // CreateCallRequest? |  (optional) 

            try
            {
                // Start a new call.
                SpatioCall result = apiInstance.CreateCall(createCallRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.CreateCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Start a new call.
    ApiResponse<SpatioCall> response = apiInstance.CreateCallWithHttpInfo(createCallRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.CreateCallWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createCallRequest** | [**CreateCallRequest?**](CreateCallRequest?.md) |  | [optional]  |

### Return type

[**SpatioCall**](SpatioCall.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created call. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createmeetingroom"></a>
# **CreateMeetingRoom**
> MeetingRoom CreateMeetingRoom (CreateMeetingRoomRequest createMeetingRoomRequest)

Create a persistent meeting room.

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
    public class CreateMeetingRoomExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var createMeetingRoomRequest = new CreateMeetingRoomRequest(); // CreateMeetingRoomRequest | 

            try
            {
                // Create a persistent meeting room.
                MeetingRoom result = apiInstance.CreateMeetingRoom(createMeetingRoomRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.CreateMeetingRoom: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateMeetingRoomWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a persistent meeting room.
    ApiResponse<MeetingRoom> response = apiInstance.CreateMeetingRoomWithHttpInfo(createMeetingRoomRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.CreateMeetingRoomWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createMeetingRoomRequest** | [**CreateMeetingRoomRequest**](CreateMeetingRoomRequest.md) |  |  |

### Return type

[**MeetingRoom**](MeetingRoom.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created room. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletecallrecording"></a>
# **DeleteCallRecording**
> void DeleteCallRecording (string recordingId)

Delete a recording.

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
    public class DeleteCallRecordingExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var recordingId = "recordingId_example";  // string | 

            try
            {
                // Delete a recording.
                apiInstance.DeleteCallRecording(recordingId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.DeleteCallRecording: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteCallRecordingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a recording.
    apiInstance.DeleteCallRecordingWithHttpInfo(recordingId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.DeleteCallRecordingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **recordingId** | **string** |  |  |

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

<a id="endcall"></a>
# **EndCall**
> void EndCall (string id)

End a call (host only).

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
    public class EndCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // End a call (host only).
                apiInstance.EndCall(id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.EndCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the EndCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // End a call (host only).
    apiInstance.EndCallWithHttpInfo(id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.EndCallWithHttpInfo: " + e.Message);
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
| **204** | Ended. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getbandwidthhistory"></a>
# **GetBandwidthHistory**
> Dictionary&lt;string, Object&gt; GetBandwidthHistory ()

Time-series bandwidth metrics.

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
    public class GetBandwidthHistoryExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);

            try
            {
                // Time-series bandwidth metrics.
                Dictionary<string, Object> result = apiInstance.GetBandwidthHistory();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.GetBandwidthHistory: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetBandwidthHistoryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Time-series bandwidth metrics.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.GetBandwidthHistoryWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.GetBandwidthHistoryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
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
| **200** | History (open shape). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getbandwidthsummary"></a>
# **GetBandwidthSummary**
> Dictionary&lt;string, Object&gt; GetBandwidthSummary ()

Aggregate bandwidth metrics.

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
    public class GetBandwidthSummaryExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);

            try
            {
                // Aggregate bandwidth metrics.
                Dictionary<string, Object> result = apiInstance.GetBandwidthSummary();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.GetBandwidthSummary: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetBandwidthSummaryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Aggregate bandwidth metrics.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.GetBandwidthSummaryWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.GetBandwidthSummaryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
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
| **200** | Summary (open shape — provider-tied). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getcall"></a>
# **GetCall**
> SpatioCall GetCall (string id)

Fetch a call.

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
    public class GetCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // Fetch a call.
                SpatioCall result = apiInstance.GetCall(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.GetCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch a call.
    ApiResponse<SpatioCall> response = apiInstance.GetCallWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.GetCallWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |

### Return type

[**SpatioCall**](SpatioCall.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Call. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getmeetingroom"></a>
# **GetMeetingRoom**
> MeetingRoom GetMeetingRoom (string id)

Fetch a meeting room.

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
    public class GetMeetingRoomExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // Fetch a meeting room.
                MeetingRoom result = apiInstance.GetMeetingRoom(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.GetMeetingRoom: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetMeetingRoomWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch a meeting room.
    ApiResponse<MeetingRoom> response = apiInstance.GetMeetingRoomWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.GetMeetingRoomWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |

### Return type

[**MeetingRoom**](MeetingRoom.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Meeting room. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="joincall"></a>
# **JoinCall**
> Dictionary&lt;string, Object&gt; JoinCall (string id)

Join a call.

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
    public class JoinCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // Join a call.
                Dictionary<string, Object> result = apiInstance.JoinCall(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.JoinCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the JoinCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Join a call.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.JoinCallWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.JoinCallWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
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
| **200** | Join state envelope (provider-tied). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="leavecall"></a>
# **LeaveCall**
> void LeaveCall (string id)

Leave a call.

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
    public class LeaveCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // Leave a call.
                apiInstance.LeaveCall(id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.LeaveCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the LeaveCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Leave a call.
    apiInstance.LeaveCallWithHttpInfo(id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.LeaveCallWithHttpInfo: " + e.Message);
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
| **204** | Left. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listactivecalls"></a>
# **ListActiveCalls**
> CallListResponse ListActiveCalls ()

List active calls.

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
    public class ListActiveCallsExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);

            try
            {
                // List active calls.
                CallListResponse result = apiInstance.ListActiveCalls();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.ListActiveCalls: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListActiveCallsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List active calls.
    ApiResponse<CallListResponse> response = apiInstance.ListActiveCallsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.ListActiveCallsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**CallListResponse**](CallListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Call list envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcallrecordings"></a>
# **ListCallRecordings**
> CallRecordingListResponse ListCallRecordings (string id)

List recordings for a call.

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
    public class ListCallRecordingsExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // List recordings for a call.
                CallRecordingListResponse result = apiInstance.ListCallRecordings(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.ListCallRecordings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCallRecordingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List recordings for a call.
    ApiResponse<CallRecordingListResponse> response = apiInstance.ListCallRecordingsWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.ListCallRecordingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |

### Return type

[**CallRecordingListResponse**](CallRecordingListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recording envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="startcallrecording"></a>
# **StartCallRecording**
> CallRecording StartCallRecording (string id)

Start a recording (host only).

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
    public class StartCallRecordingExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 

            try
            {
                // Start a recording (host only).
                CallRecording result = apiInstance.StartCallRecording(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.StartCallRecording: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the StartCallRecordingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Start a recording (host only).
    ApiResponse<CallRecording> response = apiInstance.StartCallRecordingWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.StartCallRecordingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |

### Return type

[**CallRecording**](CallRecording.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recording. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="stopcallrecording"></a>
# **StopCallRecording**
> CallRecording StopCallRecording (string id, string recordingId)

Stop an in-progress recording.

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
    public class StopCallRecordingExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 
            var recordingId = "recordingId_example";  // string | 

            try
            {
                // Stop an in-progress recording.
                CallRecording result = apiInstance.StopCallRecording(id, recordingId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.StopCallRecording: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the StopCallRecordingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Stop an in-progress recording.
    ApiResponse<CallRecording> response = apiInstance.StopCallRecordingWithHttpInfo(id, recordingId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.StopCallRecordingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |
| **recordingId** | **string** |  |  |

### Return type

[**CallRecording**](CallRecording.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recording. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatecallparticipantstate"></a>
# **UpdateCallParticipantState**
> Dictionary&lt;string, Object&gt; UpdateCallParticipantState (string id, UpdateParticipantStateRequest updateParticipantStateRequest)

Toggle participant audio/video/screen-share state.

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
    public class UpdateCallParticipantStateExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | 
            var updateParticipantStateRequest = new UpdateParticipantStateRequest(); // UpdateParticipantStateRequest | 

            try
            {
                // Toggle participant audio/video/screen-share state.
                Dictionary<string, Object> result = apiInstance.UpdateCallParticipantState(id, updateParticipantStateRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.UpdateCallParticipantState: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateCallParticipantStateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Toggle participant audio/video/screen-share state.
    ApiResponse<Dictionary<string, Object>> response = apiInstance.UpdateCallParticipantStateWithHttpInfo(id, updateParticipantStateRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.UpdateCallParticipantStateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |
| **updateParticipantStateRequest** | [**UpdateParticipantStateRequest**](UpdateParticipantStateRequest.md) |  |  |

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
| **200** | Updated state envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacecreatecall"></a>
# **WorkspaceCreateCall**
> Dictionary&lt;string, Object&gt; WorkspaceCreateCall (string org, string workspace, Dictionary<string, Object> requestBody)



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
    public class WorkspaceCreateCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceCreateCall(org, workspace, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceCreateCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceCreateCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceCreateCallWithHttpInfo(org, workspace, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceCreateCallWithHttpInfo: " + e.Message);
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

<a id="workspacecreatemeetingroom"></a>
# **WorkspaceCreateMeetingRoom**
> Dictionary&lt;string, Object&gt; WorkspaceCreateMeetingRoom (string org, string workspace, Dictionary<string, Object> requestBody)



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
    public class WorkspaceCreateMeetingRoomExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceCreateMeetingRoom(org, workspace, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceCreateMeetingRoom: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceCreateMeetingRoomWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceCreateMeetingRoomWithHttpInfo(org, workspace, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceCreateMeetingRoomWithHttpInfo: " + e.Message);
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

<a id="workspacedeletecallrecording"></a>
# **WorkspaceDeleteCallRecording**
> void WorkspaceDeleteCallRecording (string org, string workspace, string recordingId)



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
    public class WorkspaceDeleteCallRecordingExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var recordingId = "recordingId_example";  // string | 

            try
            {
                apiInstance.WorkspaceDeleteCallRecording(org, workspace, recordingId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceDeleteCallRecording: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceDeleteCallRecordingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    apiInstance.WorkspaceDeleteCallRecordingWithHttpInfo(org, workspace, recordingId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceDeleteCallRecordingWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **org** | **string** |  |  |
| **workspace** | **string** |  |  |
| **recordingId** | **string** |  |  |

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

<a id="workspaceendcall"></a>
# **WorkspaceEndCall**
> void WorkspaceEndCall (string org, string workspace, string id)



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
    public class WorkspaceEndCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                apiInstance.WorkspaceEndCall(org, workspace, id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceEndCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceEndCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    apiInstance.WorkspaceEndCallWithHttpInfo(org, workspace, id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceEndCallWithHttpInfo: " + e.Message);
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
| **204** | Ended |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacegetbandwidthhistory"></a>
# **WorkspaceGetBandwidthHistory**
> Dictionary&lt;string, Object&gt; WorkspaceGetBandwidthHistory (string org, string workspace)



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
    public class WorkspaceGetBandwidthHistoryExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceGetBandwidthHistory(org, workspace);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceGetBandwidthHistory: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceGetBandwidthHistoryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceGetBandwidthHistoryWithHttpInfo(org, workspace);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceGetBandwidthHistoryWithHttpInfo: " + e.Message);
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
| **200** | History |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacegetbandwidthsummary"></a>
# **WorkspaceGetBandwidthSummary**
> Dictionary&lt;string, Object&gt; WorkspaceGetBandwidthSummary (string org, string workspace)



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
    public class WorkspaceGetBandwidthSummaryExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceGetBandwidthSummary(org, workspace);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceGetBandwidthSummary: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceGetBandwidthSummaryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceGetBandwidthSummaryWithHttpInfo(org, workspace);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceGetBandwidthSummaryWithHttpInfo: " + e.Message);
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
| **200** | Summary |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacegetcall"></a>
# **WorkspaceGetCall**
> Dictionary&lt;string, Object&gt; WorkspaceGetCall (string org, string workspace, string id)



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
    public class WorkspaceGetCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceGetCall(org, workspace, id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceGetCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceGetCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceGetCallWithHttpInfo(org, workspace, id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceGetCallWithHttpInfo: " + e.Message);
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
| **200** | Call |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacegetmeetingroom"></a>
# **WorkspaceGetMeetingRoom**
> Dictionary&lt;string, Object&gt; WorkspaceGetMeetingRoom (string org, string workspace, string id)



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
    public class WorkspaceGetMeetingRoomExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceGetMeetingRoom(org, workspace, id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceGetMeetingRoom: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceGetMeetingRoomWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceGetMeetingRoomWithHttpInfo(org, workspace, id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceGetMeetingRoomWithHttpInfo: " + e.Message);
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
| **200** | Room |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacejoincall"></a>
# **WorkspaceJoinCall**
> Dictionary&lt;string, Object&gt; WorkspaceJoinCall (string org, string workspace, string id)



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
    public class WorkspaceJoinCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceJoinCall(org, workspace, id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceJoinCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceJoinCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceJoinCallWithHttpInfo(org, workspace, id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceJoinCallWithHttpInfo: " + e.Message);
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
| **200** | Joined |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspaceleavecall"></a>
# **WorkspaceLeaveCall**
> void WorkspaceLeaveCall (string org, string workspace, string id)



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
    public class WorkspaceLeaveCallExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                apiInstance.WorkspaceLeaveCall(org, workspace, id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceLeaveCall: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceLeaveCallWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    apiInstance.WorkspaceLeaveCallWithHttpInfo(org, workspace, id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceLeaveCallWithHttpInfo: " + e.Message);
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
| **204** | Left |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacelistactivecalls"></a>
# **WorkspaceListActiveCalls**
> Dictionary&lt;string, Object&gt; WorkspaceListActiveCalls (string org, string workspace)



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
    public class WorkspaceListActiveCallsExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceListActiveCalls(org, workspace);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceListActiveCalls: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceListActiveCallsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceListActiveCallsWithHttpInfo(org, workspace);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceListActiveCallsWithHttpInfo: " + e.Message);
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
| **200** | Calls |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacelistcallrecordings"></a>
# **WorkspaceListCallRecordings**
> Dictionary&lt;string, Object&gt; WorkspaceListCallRecordings (string org, string workspace, string id)



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
    public class WorkspaceListCallRecordingsExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceListCallRecordings(org, workspace, id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceListCallRecordings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceListCallRecordingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceListCallRecordingsWithHttpInfo(org, workspace, id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceListCallRecordingsWithHttpInfo: " + e.Message);
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
| **200** | Recordings |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacestartcallrecording"></a>
# **WorkspaceStartCallRecording**
> Dictionary&lt;string, Object&gt; WorkspaceStartCallRecording (string org, string workspace, string id)



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
    public class WorkspaceStartCallRecordingExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceStartCallRecording(org, workspace, id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceStartCallRecording: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceStartCallRecordingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceStartCallRecordingWithHttpInfo(org, workspace, id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceStartCallRecordingWithHttpInfo: " + e.Message);
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
| **200** | Started |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspacestopcallrecording"></a>
# **WorkspaceStopCallRecording**
> Dictionary&lt;string, Object&gt; WorkspaceStopCallRecording (string org, string workspace, string id, string recordingId)



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
    public class WorkspaceStopCallRecordingExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 
            var recordingId = "recordingId_example";  // string | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceStopCallRecording(org, workspace, id, recordingId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceStopCallRecording: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceStopCallRecordingWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceStopCallRecordingWithHttpInfo(org, workspace, id, recordingId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceStopCallRecordingWithHttpInfo: " + e.Message);
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
| **recordingId** | **string** |  |  |

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
| **200** | Stopped |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="workspaceupdatecallparticipant"></a>
# **WorkspaceUpdateCallParticipant**
> Dictionary&lt;string, Object&gt; WorkspaceUpdateCallParticipant (string org, string workspace, string id, Dictionary<string, Object> requestBody)



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
    public class WorkspaceUpdateCallParticipantExample
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
            var apiInstance = new CallsApi(httpClient, config, httpClientHandler);
            var org = "org_example";  // string | 
            var workspace = "workspace_example";  // string | 
            var id = "id_example";  // string | 
            var requestBody = new Dictionary<string, Object>(); // Dictionary<string, Object> | 

            try
            {
                Dictionary<string, Object> result = apiInstance.WorkspaceUpdateCallParticipant(org, workspace, id, requestBody);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CallsApi.WorkspaceUpdateCallParticipant: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the WorkspaceUpdateCallParticipantWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    ApiResponse<Dictionary<string, Object>> response = apiInstance.WorkspaceUpdateCallParticipantWithHttpInfo(org, workspace, id, requestBody);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CallsApi.WorkspaceUpdateCallParticipantWithHttpInfo: " + e.Message);
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

