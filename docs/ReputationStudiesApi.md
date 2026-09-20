# \ReputationStudiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_reputation_report**](ReputationStudiesApi.md#get_reputation_report) | **GET** /reputation/reports/{id} | Get reputation report scores
[**get_study**](ReputationStudiesApi.md#get_study) | **GET** /studies/{id} | Get a custom AI study
[**get_study_report**](ReputationStudiesApi.md#get_study_report) | **GET** /studies/{id}/reports/{report_id} | Get custom study report scores
[**list_reputation_reports**](ReputationStudiesApi.md#list_reputation_reports) | **GET** /reputation/reports | List reputation reports
[**list_studies**](ReputationStudiesApi.md#list_studies) | **GET** /studies | List custom AI studies



## get_reputation_report

> get_reputation_report(id, project_id, page, per_page, model, brand, dimension, output)
Get reputation report scores

One reputation report's scores as flat rows: one row per analyst model, brand, dimension and attribute, with its 0-100 score and the reasoning the model gave. Scores come from several analyst models independently, so compare models rather than averaging them blindly.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **String** | The report id from GET /reputation/reports | [required] |
**project_id** | **i32** | Project ID | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Restrict to one analyst model |  |
**brand** | Option<**String**> | Restrict to one brand name, or a comma-separated list |  |
**dimension** | Option<**String**> | Restrict to one reputation dimension key |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_study

> get_study(id)
Get a custom AI study

One study with its brief, the subjects it compares, the dimensions it scores them on, and its report history. Use the ids in `reports` with GET /studies/{id}/reports/{report_id}.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** |  | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_study_report

> get_study_report(id, report_id, page, per_page, model, subject, dimension, output)
Get custom study report scores

One custom-study report's scores as flat rows: one row per analyst model, subject, dimension and attribute, with its 0-100 score and the reasoning the model gave.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** |  | [required] |
**report_id** | **String** | The report id from GET /studies/{id} | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Restrict to one analyst model |  |
**subject** | Option<**String**> | Restrict to one subject name, or a comma-separated list |  |
**dimension** | Option<**String**> | Restrict to one dimension key |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_reputation_reports

> list_reputation_reports(project_id, page, per_page, output)
List reputation reports

The monthly multi-model analyst reports scoring the tracked brand and its competitors, newest first. Pending and failed reports are included on purpose: whether this month ran at all is often the question. Each row carries the report id, its status, and which analyst models produced data. Requires reputation monitoring to be enabled on the account.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_studies

> list_studies(project_id, status, page, per_page, output)
List custom AI studies

The custom AI studies defined on the account: analyst reports over any set of subjects (brands, sectors, topics) and any set of dimensions. Studies belong to the ACCOUNT, not to a project, so project_id is an optional filter here and account-level studies are returned whichever project you filter by. A team member whose project access is restricted sees only the studies of the projects they can reach. Requires reputation monitoring to be enabled on the account.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | Option<**i32**> | Restrict to studies attached to this project (plus account-level ones) |  |
**status** | Option<**String**> |  |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

