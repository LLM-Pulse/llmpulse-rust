# \MetricsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_prompt_summary**](MetricsApi.md#get_prompt_summary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary
[**get_share_of_voice**](MetricsApi.md#get_share_of_voice) | **GET** /metrics/sov | Share of Voice
[**get_summary**](MetricsApi.md#get_summary) | **GET** /metrics/summary | Aggregated metrics summary
[**get_timeseries**](MetricsApi.md#get_timeseries) | **GET** /metrics/timeseries | Time-series metrics
[**get_top_sources**](MetricsApi.md#get_top_sources) | **GET** /metrics/top_sources | Top cited sources



## get_prompt_summary

> models::PromptSummaryResponse get_prompt_summary(project_id, range, from, to, breakdown, model, collection_id, country_code, language_code, prompt, prompt_type, brand_kind, sort, sort_dir, page, per_page, output)
Per-prompt metrics summary

Paginated per-prompt aggregated metrics. Returns responses, mentions, citations, mention_rate, citation_rate, avg_mention_position and avg_position per prompt. Citations and citation rate include visible citations and background source references; avg_position uses visible citations only. Pass `breakdown=model` to split each prompt by model.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**breakdown** | Option<**String**> | Add per-(prompt, model) rows to the output |  |
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**sort** | Option<**String**> |  |  |[default to responses]
**sort_dir** | Option<**String**> |  |  |[default to desc]
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::PromptSummaryResponse**](PromptSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_share_of_voice

> models::SovResponse get_share_of_voice(project_id, range, from, to, granularity, competitors, model, collection_id, prompt, prompt_type, brand_kind, output, view)
Share of Voice

Share of Voice breakdown comparing your project to competitors. Returns over_time, current snapshot, and a Top-4 + Others breakdown.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**granularity** | Option<**String**> |  |  |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |
**view** | Option<**String**> | Which Share of Voice projection to flatten. Only valid together with 'output'. 'over_time' (default) is one row per date and actor, 'current' the ranked snapshot, 'breakdown' the Top 4 plus Others. |  |[default to over_time]

### Return type

[**models::SovResponse**](SovResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_summary

> models::SummaryResponse get_summary(project_id, metrics, granularity, range, from, to, competitors, model, collection_id, prompt, prompt_type, brand_kind, output)
Aggregated metrics summary

Same as /metrics/timeseries but adds a `summary` block with total/min/max/last per metric per actor, plus a `position_distribution` block (Position 1, Position 2, Position 3+). Citations and citation rate include visible citations and background source references. Background references use position 0 and are excluded from avg_position and position distributions. `total` is a SUM for count metrics (mentions, citations, responses) and an AVERAGE across periods for rate/percentage and average metrics (visibility/mention_rate, citation_rate, ai_visibility_score, sentiment shares, avg_position, avg_mention_position, net_sentiment); rates are never summed. Each summary row carries an `aggregation` field (`sum` or `average`).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**metrics** | Option<**String**> | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. |  |
**granularity** | Option<**String**> |  |  |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::SummaryResponse**](SummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_timeseries

> models::TimeseriesResponse get_timeseries(project_id, metrics, granularity, range, from, to, competitors, model, collection_id, country_code, language_code, prompt, prompt_type, brand_kind, include_project, output)
Time-series metrics

Returns time-series data for one or more metrics, broken down by actor (project + competitors). Supports day/week/month granularity, with sticky carry-forward semantics for week/month aggregates.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**metrics** | Option<**String**> | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. |  |
**granularity** | Option<**String**> |  |  |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**include_project** | Option<**bool**> |  |  |[default to true]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::TimeseriesResponse**](TimeseriesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_top_sources

> models::TopSourcesResponse get_top_sources(project_id, range, from, to, model, collection_id, country_code, language_code, prompt, prompt_type, brand_kind, sort, query, page, per_page, output)
Top cited sources

Registrable domains most frequently cited in AI responses for the project, including visible citations and background source references. This endpoint remains a domain rollup when exact-subdomain matching is enabled. Results can be sorted by total responses, average mention rate, or average visibility.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**sort** | Option<**String**> |  |  |[default to total_responses]
**query** | Option<**String**> | Filter domains by case-insensitive partial match |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::TopSourcesResponse**](TopSourcesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

