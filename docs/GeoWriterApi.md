# \GeoWriterApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_intelligence_task**](GeoWriterApi.md#create_intelligence_task) | **POST** /intelligence_tasks | Create a GEO Writer task
[**get_intelligence_task**](GeoWriterApi.md#get_intelligence_task) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task
[**list_intelligence_tasks**](GeoWriterApi.md#list_intelligence_tasks) | **GET** /intelligence_tasks | List GEO Writer tasks
[**revert_intelligence_task_content**](GeoWriterApi.md#revert_intelligence_task_content) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content
[**update_intelligence_task_content**](GeoWriterApi.md#update_intelligence_task_content) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content



## create_intelligence_task

> models::IntelligenceTask create_intelligence_task(intelligence_task_create_request)
Create a GEO Writer task

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**intelligence_task_create_request** | [**IntelligenceTaskCreateRequest**](IntelligenceTaskCreateRequest.md) |  | [required] |

### Return type

[**models::IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_intelligence_task

> models::IntelligenceTask get_intelligence_task(project_id, id)
Get a GEO Writer task

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**id** | **String** | Numeric task ID or public_id string token | [required] |

### Return type

[**models::IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_intelligence_tasks

> list_intelligence_tasks(project_id, task_type, status, page, per_page)
List GEO Writer tasks

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**task_type** | Option<**String**> |  |  |
**status** | Option<**String**> |  |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## revert_intelligence_task_content

> models::IntelligenceTask revert_intelligence_task_content(project_id, id)
Revert GEO Writer task content

Discards every manual edit on the task and restores the output exactly as it was generated. Returns ERR_INVALID_PARAM when the task has no manual edits. Requires a `read_write` scope API key and, for team members, update permission on GEO Writer.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**id** | **String** | Numeric task ID or public_id string token | [required] |

### Return type

[**models::IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_intelligence_task_content

> models::IntelligenceTaskUpdateResponse update_intelligence_task_content(id, intelligence_task_update_request)
Edit GEO Writer task content

Edits the text of a completed task in place. `edits` maps dotted paths into result_data (for example `title` or `sections.0.content`) to replacement text. Only string fields that already exist can change: a path that does not resolve to text, a blank `title`, a value over 20,000 characters or an empty `edits` object is rejected with ERR_INVALID_PARAM and nothing is written. Values identical to the stored text are ignored, and the response lists the paths that actually changed. The first edit keeps a copy of the generated output so POST /intelligence_tasks/{id}/revert can restore it; regenerating the task replaces the edited content. Requires a `read_write` scope API key and, for team members, update permission on GEO Writer.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **String** | Numeric task ID or public_id string token | [required] |
**intelligence_task_update_request** | [**IntelligenceTaskUpdateRequest**](IntelligenceTaskUpdateRequest.md) |  | [required] |

### Return type

[**models::IntelligenceTaskUpdateResponse**](IntelligenceTaskUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

