# \TechnicalGeoReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_technical_geo_reports**](TechnicalGeoReportsApi.md#create_technical_geo_reports) | **POST** /technical_geo_reports | Run technical GEO analysis
[**get_technical_geo_report**](TechnicalGeoReportsApi.md#get_technical_geo_report) | **GET** /technical_geo_reports/{id} | Get a technical GEO report
[**list_technical_geo_reports**](TechnicalGeoReportsApi.md#list_technical_geo_reports) | **GET** /technical_geo_reports | List technical GEO reports
[**revert_technical_geo_report_content**](TechnicalGeoReportsApi.md#revert_technical_geo_report_content) | **POST** /technical_geo_reports/{id}/revert_content | Revert llms.txt report content
[**update_technical_geo_report_content**](TechnicalGeoReportsApi.md#update_technical_geo_report_content) | **PATCH** /technical_geo_reports/{id}/content | Edit llms.txt report content



## create_technical_geo_reports

> create_technical_geo_reports(create_technical_geo_reports_request)
Run technical GEO analysis

Launches the full nine-report technical GEO analysis bundle for a URL + country. The bundle starts only when at least nine daily units remain. Each successfully created report uses one unit; a report that is not created uses none. Daily allocations vary by account. Each report runs in a background job. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_technical_geo_reports_request** | [**CreateTechnicalGeoReportsRequest**](CreateTechnicalGeoReportsRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_technical_geo_report

> get_technical_geo_report(project_id, report_type, id)
Get a technical GEO report

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website's own language, requested as auto or chosen in the app, and for every other report type); a completed llms_txt result_data also returns content_version (send it back to PATCH /technical_geo_reports/{id}/content), manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, kept from the first manual edit in the app, the API or MCP) and metadata.output_language_code.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**report_type** | **String** |  | [required] |
**id** | **i32** | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_technical_geo_reports

> list_technical_geo_reports(project_id, report_type, status, batch_id, page, per_page)
List technical GEO reports

Lists reports of one technical GEO type for a project, newest first. Use agent_readiness for the AI/Agent Readiness report.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**report_type** | **String** |  | [required] |
**status** | Option<**String**> | Optional status filter; valid values depend on report_type |  |
**batch_id** | Option<**i32**> | Optional batch id returned when the report bundle was created |  |
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


## revert_technical_geo_report_content

> models::LlmsTxtTechnicalGeoReport revert_technical_geo_report_content(id, technical_geo_report_content_revert_request)
Revert llms.txt report content

Discards every manual edit on the llms_txt report and restores the llms.txt and llms-full.txt files exactly as they were generated. Returns ERR_INVALID_PARAM when the report has no manual edits or report_type is not llms_txt. Requires a `read_write` scope API key and, for team members, create permission on GEO Optimization.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | [required] |
**technical_geo_report_content_revert_request** | [**TechnicalGeoReportContentRevertRequest**](TechnicalGeoReportContentRevertRequest.md) |  | [required] |

### Return type

[**models::LlmsTxtTechnicalGeoReport**](LlmsTxtTechnicalGeoReport.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_technical_geo_report_content

> models::TechnicalGeoReportContentUpdateResponse update_technical_geo_report_content(id, technical_geo_report_content_update_request)
Edit llms.txt report content

Replaces the llms.txt and llms-full.txt files of a completed llms_txt report in place, without generating them again. `edits` maps llms_txt and/or llms_full_txt to the full replacement text. `content_version` must equal result_data.content_version of the report as last read; when the report changed since, the edit is refused as stale and the message names the current version. A missing or stale content_version, a blank file, a file over 200,000 characters, a value that is not text, an unknown file key, an empty `edits` object, a report that has not completed or a report_type other than llms_txt is rejected with ERR_INVALID_PARAM and nothing is written. Files are stored with Unix line endings and one trailing newline. A file identical to the stored one is ignored, and the response lists the files that actually changed. The first edit keeps the generated files in original_llms_txt_content and original_llms_full_txt_content so POST /technical_geo_reports/{id}/revert_content can restore them; running the report again creates a new report without these edits. Requires a `read_write` scope API key and, for team members, create permission on GEO Optimization.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | [required] |
**technical_geo_report_content_update_request** | [**TechnicalGeoReportContentUpdateRequest**](TechnicalGeoReportContentUpdateRequest.md) |  | [required] |

### Return type

[**models::TechnicalGeoReportContentUpdateResponse**](TechnicalGeoReportContentUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

