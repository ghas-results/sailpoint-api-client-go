# \SavedSearchApi

All URIs are relative to *https://sailpoint.api.identitynow.com/v3*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CreateSavedSearch**](SavedSearchApi.md#CreateSavedSearch) | **Post** /saved-searches | Create a saved search
[**DeleteSavedSearch**](SavedSearchApi.md#DeleteSavedSearch) | **Delete** /saved-searches/{id} | Delete a document by ID
[**ExecuteSavedSearch**](SavedSearchApi.md#ExecuteSavedSearch) | **Post** /saved-searches/{id}/execute | Execute a saved search by ID
[**GetSavedSearch**](SavedSearchApi.md#GetSavedSearch) | **Get** /saved-searches/{id} | Return a saved search by ID
[**ListSavedSearches**](SavedSearchApi.md#ListSavedSearches) | **Get** /saved-searches | Return a list of Saved Searches
[**UpdateSavedSearch**](SavedSearchApi.md#UpdateSavedSearch) | **Put** /saved-searches/{id} | Updates an existing saved search 



## CreateSavedSearch

> SavedSearch CreateSavedSearch(ctx).CreateSavedSearchRequest(createSavedSearchRequest).Execute()

Create a saved search



### Example

```go
package main

import (
    "context"
    "fmt"
    "os"
    openapiclient "./openapi"
)

func main() {
    createSavedSearchRequest := *openapiclient.NewCreateSavedSearchRequest([]openapiclient.Index{openapiclient.Index("accessprofiles")}, "@accounts(disabled:true)") // CreateSavedSearchRequest | The saved search to persist.

    configuration := openapiclient.NewConfiguration()
    apiClient := openapiclient.NewAPIClient(configuration)
    resp, r, err := apiClient.SavedSearchApi.CreateSavedSearch(context.Background()).CreateSavedSearchRequest(createSavedSearchRequest).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `SavedSearchApi.CreateSavedSearch``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
    }
    // response from `CreateSavedSearch`: SavedSearch
    fmt.Fprintf(os.Stdout, "Response from `SavedSearchApi.CreateSavedSearch`: %v\n", resp)
}
```

### Path Parameters



### Other Parameters

Other parameters are passed through a pointer to a apiCreateSavedSearchRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **createSavedSearchRequest** | [**CreateSavedSearchRequest**](CreateSavedSearchRequest.md) | The saved search to persist. | 

### Return type

[**SavedSearch**](SavedSearch.md)

### Authorization

[oauth2](../README.md#oauth2), [oauth2](../README.md#oauth2)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteSavedSearch

> DeleteSavedSearch(ctx, id).Execute()

Delete a document by ID



### Example

```go
package main

import (
    "context"
    "fmt"
    "os"
    openapiclient "./openapi"
)

func main() {
    id := "2c91808568c529c60168cca6f90c1313" // string | ID of the requested document.

    configuration := openapiclient.NewConfiguration()
    apiClient := openapiclient.NewAPIClient(configuration)
    resp, r, err := apiClient.SavedSearchApi.DeleteSavedSearch(context.Background(), id).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `SavedSearchApi.DeleteSavedSearch``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
    }
}
```

### Path Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**id** | **string** | ID of the requested document. | 

### Other Parameters

Other parameters are passed through a pointer to a apiDeleteSavedSearchRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


### Return type

 (empty response body)

### Authorization

[oauth2](../README.md#oauth2), [oauth2](../README.md#oauth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ExecuteSavedSearch

> ExecuteSavedSearch(ctx, id).SearchArguments(searchArguments).Execute()

Execute a saved search by ID



### Example

```go
package main

import (
    "context"
    "fmt"
    "os"
    openapiclient "./openapi"
)

func main() {
    id := "2c91808568c529c60168cca6f90c1313" // string | ID of the requested document.
    searchArguments := *openapiclient.NewSearchArguments() // SearchArguments | When saved search execution is triggered by a scheduled search, *scheduleId* will specify the ID of the triggering scheduled search.  If *scheduleId* is not specified (when execution is triggered by a UI test), the *owner* and *recipients* arguments must be provided. 

    configuration := openapiclient.NewConfiguration()
    apiClient := openapiclient.NewAPIClient(configuration)
    resp, r, err := apiClient.SavedSearchApi.ExecuteSavedSearch(context.Background(), id).SearchArguments(searchArguments).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `SavedSearchApi.ExecuteSavedSearch``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
    }
}
```

### Path Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**id** | **string** | ID of the requested document. | 

### Other Parameters

Other parameters are passed through a pointer to a apiExecuteSavedSearchRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **searchArguments** | [**SearchArguments**](SearchArguments.md) | When saved search execution is triggered by a scheduled search, *scheduleId* will specify the ID of the triggering scheduled search.  If *scheduleId* is not specified (when execution is triggered by a UI test), the *owner* and *recipients* arguments must be provided.  | 

### Return type

 (empty response body)

### Authorization

[oauth2](../README.md#oauth2), [oauth2](../README.md#oauth2)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetSavedSearch

> SavedSearch GetSavedSearch(ctx, id).Execute()

Return a saved search by ID



### Example

```go
package main

import (
    "context"
    "fmt"
    "os"
    openapiclient "./openapi"
)

func main() {
    id := "2c91808568c529c60168cca6f90c1313" // string | ID of the requested document.

    configuration := openapiclient.NewConfiguration()
    apiClient := openapiclient.NewAPIClient(configuration)
    resp, r, err := apiClient.SavedSearchApi.GetSavedSearch(context.Background(), id).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `SavedSearchApi.GetSavedSearch``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
    }
    // response from `GetSavedSearch`: SavedSearch
    fmt.Fprintf(os.Stdout, "Response from `SavedSearchApi.GetSavedSearch`: %v\n", resp)
}
```

### Path Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**id** | **string** | ID of the requested document. | 

### Other Parameters

Other parameters are passed through a pointer to a apiGetSavedSearchRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


### Return type

[**SavedSearch**](SavedSearch.md)

### Authorization

[oauth2](../README.md#oauth2), [oauth2](../README.md#oauth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ListSavedSearches

> []SavedSearch ListSavedSearches(ctx).Offset(offset).Limit(limit).Count(count).Filters(filters).Execute()

Return a list of Saved Searches



### Example

```go
package main

import (
    "context"
    "fmt"
    "os"
    openapiclient "./openapi"
)

func main() {
    offset := int32(0) // int32 | Offset into the full result set. Usually specified with *limit* to paginate through the results. See [V3 API Standard Collection Parameters](https://developer.sailpoint.com/idn/api/standard-collection-parameters) for more information. (optional) (default to 0)
    limit := int32(250) // int32 | Max number of results to return. See [V3 API Standard Collection Parameters](https://developer.sailpoint.com/idn/api/standard-collection-parameters) for more information. (optional) (default to 250)
    count := true // bool | If *true* it will populate the *X-Total-Count* response header with the number of results that would be returned if *limit* and *offset* were ignored.  Since requesting a total count can have a performance impact, it is recommended not to send **count=true** if that value will not be used.  See [V3 API Standard Collection Parameters](https://developer.sailpoint.com/idn/api/standard-collection-parameters) for more information. (optional) (default to false)
    filters := "public eq true" // string | An expression used to constrain the result set using the filtering syntax described in [V3 API Standard Collection Parameters](https://developer.sailpoint.com/idn/api/standard-collection-parameters#filtering-results).  Allowed filter properties: *owner.id*, *public*  Allowed filter operator: *eq*  **Example filters**:  ```owner.id eq \"0de46054-fe90-434a-b84e-c6b3359d0c64\"``` -- returns saved searches for the specified owner ID  ```public eq true``` -- returns all public saved searches  ```owner.id eq me or public eq true``` -- returns all of the current user's saved searches as well as all public saved searches belonging to other users in the current org  (optional)

    configuration := openapiclient.NewConfiguration()
    apiClient := openapiclient.NewAPIClient(configuration)
    resp, r, err := apiClient.SavedSearchApi.ListSavedSearches(context.Background()).Offset(offset).Limit(limit).Count(count).Filters(filters).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `SavedSearchApi.ListSavedSearches``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
    }
    // response from `ListSavedSearches`: []SavedSearch
    fmt.Fprintf(os.Stdout, "Response from `SavedSearchApi.ListSavedSearches`: %v\n", resp)
}
```

### Path Parameters



### Other Parameters

Other parameters are passed through a pointer to a apiListSavedSearchesRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int32** | Offset into the full result set. Usually specified with *limit* to paginate through the results. See [V3 API Standard Collection Parameters](https://developer.sailpoint.com/idn/api/standard-collection-parameters) for more information. | [default to 0]
 **limit** | **int32** | Max number of results to return. See [V3 API Standard Collection Parameters](https://developer.sailpoint.com/idn/api/standard-collection-parameters) for more information. | [default to 250]
 **count** | **bool** | If *true* it will populate the *X-Total-Count* response header with the number of results that would be returned if *limit* and *offset* were ignored.  Since requesting a total count can have a performance impact, it is recommended not to send **count&#x3D;true** if that value will not be used.  See [V3 API Standard Collection Parameters](https://developer.sailpoint.com/idn/api/standard-collection-parameters) for more information. | [default to false]
 **filters** | **string** | An expression used to constrain the result set using the filtering syntax described in [V3 API Standard Collection Parameters](https://developer.sailpoint.com/idn/api/standard-collection-parameters#filtering-results).  Allowed filter properties: *owner.id*, *public*  Allowed filter operator: *eq*  **Example filters**:  &#x60;&#x60;&#x60;owner.id eq \&quot;0de46054-fe90-434a-b84e-c6b3359d0c64\&quot;&#x60;&#x60;&#x60; -- returns saved searches for the specified owner ID  &#x60;&#x60;&#x60;public eq true&#x60;&#x60;&#x60; -- returns all public saved searches  &#x60;&#x60;&#x60;owner.id eq me or public eq true&#x60;&#x60;&#x60; -- returns all of the current user&#39;s saved searches as well as all public saved searches belonging to other users in the current org  | 

### Return type

[**[]SavedSearch**](SavedSearch.md)

### Authorization

[oauth2](../README.md#oauth2), [oauth2](../README.md#oauth2)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateSavedSearch

> SavedSearch UpdateSavedSearch(ctx, id).SavedSearch(savedSearch).Execute()

Updates an existing saved search 



### Example

```go
package main

import (
    "context"
    "fmt"
    "os"
    openapiclient "./openapi"
)

func main() {
    id := "2c91808568c529c60168cca6f90c1313" // string | ID of the requested document.
    savedSearch := *openapiclient.NewSavedSearch([]openapiclient.Index{openapiclient.Index("accessprofiles")}, "@accounts(disabled:true)") // SavedSearch | The saved search to persist.

    configuration := openapiclient.NewConfiguration()
    apiClient := openapiclient.NewAPIClient(configuration)
    resp, r, err := apiClient.SavedSearchApi.UpdateSavedSearch(context.Background(), id).SavedSearch(savedSearch).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `SavedSearchApi.UpdateSavedSearch``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
    }
    // response from `UpdateSavedSearch`: SavedSearch
    fmt.Fprintf(os.Stdout, "Response from `SavedSearchApi.UpdateSavedSearch`: %v\n", resp)
}
```

### Path Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**id** | **string** | ID of the requested document. | 

### Other Parameters

Other parameters are passed through a pointer to a apiUpdateSavedSearchRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **savedSearch** | [**SavedSearch**](SavedSearch.md) | The saved search to persist. | 

### Return type

[**SavedSearch**](SavedSearch.md)

### Authorization

[oauth2](../README.md#oauth2), [oauth2](../README.md#oauth2)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

