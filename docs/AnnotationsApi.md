# \AnnotationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_annotation**](AnnotationsApi.md#create_annotation) | **POST** /annotations | Create a timeline annotation
[**delete_annotation**](AnnotationsApi.md#delete_annotation) | **DELETE** /annotations/{id} | Delete a timeline annotation
[**list_annotations**](AnnotationsApi.md#list_annotations) | **GET** /annotations | List timeline annotations
[**update_annotation**](AnnotationsApi.md#update_annotation) | **PATCH** /annotations/{id} | Update a timeline annotation



## create_annotation

> create_annotation(create_annotation_request)
Create a timeline annotation

Marks a date in the project timeseries with a title + description. Available on every plan. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_annotation_request** | [**CreateAnnotationRequest**](CreateAnnotationRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_annotation

> delete_annotation(project_id, id)
Delete a timeline annotation

Deletes an annotation. Same ownership rule as PATCH. Available on every plan and requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**id** | **i32** |  | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_annotations

> list_annotations(project_id, from, to, annotation_category_id, page, per_page)
List timeline annotations

Lists project timeline annotations, newest first. Rows can come from manual notes, project automations, GEO tests, or platform events. The origin field distinguishes them; editable says whether the requesting user may modify the row. Available on every plan.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**from** | Option<**chrono::NaiveDate**> |  |  |
**to** | Option<**chrono::NaiveDate**> |  |  |
**annotation_category_id** | Option<**i32**> |  |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_annotation

> update_annotation(id, update_annotation_request)
Update a timeline annotation

Updates title, description, annotation_date, color and/or annotation_category_id. Only user-created annotations belonging to the requesting user can be updated (system annotations never). Available on every plan and requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** |  | [required] |
**update_annotation_request** | [**UpdateAnnotationRequest**](UpdateAnnotationRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

