# \AiModelInsightsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_ai_model_insights_summary**](AiModelInsightsApi.md#get_ai_model_insights_summary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary
[**get_ai_model_position_distribution**](AiModelInsightsApi.md#get_ai_model_position_distribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison
[**get_ai_overview_results**](AiModelInsightsApi.md#get_ai_overview_results) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability
[**get_declined_answers**](AiModelInsightsApi.md#get_declined_answers) | **GET** /reports/ai_model_insights/declined_answers | Declined answers (decline rate)



## get_ai_model_insights_summary

> models::AiModelInsightsSummaryResponse get_ai_model_insights_summary(project_id, range, from, to, granularity, collection_id, country_code, language_code, prompt_type, brand_kind, competitors)
AI Model Insights summary

Per-model mentions, citations, brand net sentiment with raw counts, weighted visibility totals/shares, plus actor matrices. All actor entries use the standard shape `{ type, id, competitor_id, name, domain }` with bare (scheme-less) domains. Rows cover the AI models the account has enabled or that answered in the window. A share, net sentiment or market share value with nothing behind it is null; counts, totals and weighted visibility scores stay 0. The sentiment sections (brand_net_sentiment_by_model and sentiment_market_share) need the Growth plan or above: below it they are left out and listed in `plan_required_fields`, which is always present and empty when nothing is left out.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**granularity** | Option<**String**> |  |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**competitors** | Option<**String**> | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) |  |

### Return type

[**models::AiModelInsightsSummaryResponse**](AiModelInsightsSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_ai_model_position_distribution

> get_ai_model_position_distribution(project_id, range, from, to, granularity, collection_id, country_code, language_code, prompt_type, brand_kind, model, brand1, brand2)
Position distribution comparison

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**granularity** | Option<**String**> |  |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**model** | Option<**String**> | Restrict the comparison to one AI model of AI Model Insights, whether or not that model is enabled for the API key's user. Any other value returns 422 ERR_INVALID_PARAM (invalid model). |  |
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
**range** | Option<**i32**> | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**granularity** | Option<**String**> |  |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
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


## get_declined_answers

> models::AiModelDeclinedAnswersResponse get_declined_answers(project_id, range, from, to, model, collection_id, country_code, language_code, prompt_type, brand_kind, page, per_page)
Declined answers (decline rate)

The Declined answers tab of AI Model Insights. A model declines a prompt for its own safety filters (safety_filter) or because it refuses the topic itself, such as tobacco, gambling or alcohol (topic_refusal); today only Gemini declines. A declined answer counts as no answer and never lowers visibility. The chart has one point per tracking period at the account's cadence that holds an answer of the model, and the window starts at the tracking period holding its first day.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**model** | Option<**String**> | The model whose declines to read, whether or not it is enabled for the API key's user. Default: gemini. Any other model returns 422 ERR_INVALID_PARAM (invalid model). |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]

### Return type

[**models::AiModelDeclinedAnswersResponse**](AiModelDeclinedAnswersResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

