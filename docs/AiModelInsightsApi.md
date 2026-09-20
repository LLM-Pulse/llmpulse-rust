# \AiModelInsightsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_ai_model_insights_summary**](AiModelInsightsApi.md#get_ai_model_insights_summary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary
[**get_ai_model_position_distribution**](AiModelInsightsApi.md#get_ai_model_position_distribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison
[**get_ai_overview_results**](AiModelInsightsApi.md#get_ai_overview_results) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability



## get_ai_model_insights_summary

> get_ai_model_insights_summary(project_id, range, from, to, granularity, collection_id, country_code, language_code, prompt_type, brand_kind, competitors)
AI Model Insights summary

Per-model mentions, citations, brand net sentiment with raw counts, weighted visibility totals/shares, plus actor matrices. All actor entries use the standard shape `{ type, id, competitor_id, name, domain }` with bare (scheme-less) domains.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**granularity** | Option<**String**> |  |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_ai_model_position_distribution

> get_ai_model_position_distribution(project_id, range, from, to, granularity, collection_id, country_code, language_code, prompt_type, brand_kind, model, brand1, brand2)
Position distribution comparison

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**granularity** | Option<**String**> |  |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**brand1** | Option<**i32**> | Competitor ID for the first comparison brand (omit to compare project brand) |  |
**brand2** | Option<**i32**> |  |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_ai_overview_results

> get_ai_overview_results(project_id, range, from, to, granularity, collection_id, country_code, language_code, prompt_type, brand_kind, page, per_page)
Google AI Overview result availability

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**granularity** | Option<**String**> |  |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
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

