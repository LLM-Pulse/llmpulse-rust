# \MentionsCitationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**list_all_citations**](MentionsCitationsApi.md#list_all_citations) | **GET** /dimensions/all_citations | List all citations (brand + competitor)
[**list_all_mentions**](MentionsCitationsApi.md#list_all_mentions) | **GET** /dimensions/all_mentions | List all mentions (brand + competitor)
[**list_citations**](MentionsCitationsApi.md#list_citations) | **GET** /dimensions/citations | List brand citations
[**list_competitor_citations**](MentionsCitationsApi.md#list_competitor_citations) | **GET** /dimensions/competitor_citations | List competitor citations
[**list_competitor_mentions**](MentionsCitationsApi.md#list_competitor_mentions) | **GET** /dimensions/competitor_mentions | List competitor mentions
[**list_mentions**](MentionsCitationsApi.md#list_mentions) | **GET** /dimensions/mentions | List brand mentions



## list_all_citations

> list_all_citations(project_id, competitors, page, per_page, model, collection_id, prompt, from, to, output)
List all citations (brand + competitor)

Unified citations stream with an `actor_type` field on each record. Includes visible citations and background source references; background references use position 0, meaning no visible rank.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_all_mentions

> list_all_mentions(project_id, competitors, page, per_page, model, collection_id, prompt, from, to, output)
List all mentions (brand + competitor)

Unified mentions stream. Each record has an `actor_type` field (`project` or `competitor`) so the same payload covers both.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_citations

> list_citations(project_id, page, per_page, model, collection_id, country_code, language_code, prompt, from, to, output)
List brand citations

Includes visible citations and background source references. Background references use position 0, meaning no visible rank.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_competitor_citations

> list_competitor_citations(project_id, competitors, page, per_page, model, collection_id, prompt, from, to, output)
List competitor citations

Includes visible citations and background source references. Background references use position 0, meaning no visible rank.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_competitor_mentions

> list_competitor_mentions(project_id, competitors, page, per_page, model, collection_id, prompt, from, to, output)
List competitor mentions

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_mentions

> list_mentions(project_id, page, per_page, model, collection_id, country_code, language_code, prompt, from, to, output)
List brand mentions

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

