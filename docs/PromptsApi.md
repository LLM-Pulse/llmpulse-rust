# \PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_prompts**](PromptsApi.md#create_prompts) | **POST** /prompts | Bulk-create prompts
[**delete_prompt**](PromptsApi.md#delete_prompt) | **DELETE** /prompts/{id} | Delete a prompt
[**list_prompt_executions**](PromptsApi.md#list_prompt_executions) | **GET** /dimensions/prompt_executions | List prompt executions
[**list_prompts**](PromptsApi.md#list_prompts) | **GET** /dimensions/prompts | List prompts
[**list_query_fan_outs**](PromptsApi.md#list_query_fan_outs) | **GET** /dimensions/query_fan_outs | List query fan-out



## create_prompts

> models::PromptsCreateResponse create_prompts(prompts_create_request)
Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**prompts_create_request** | [**PromptsCreateRequest**](PromptsCreateRequest.md) |  | [required] |

### Return type

[**models::PromptsCreateResponse**](PromptsCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_prompt

> delete_prompt(project_id, id)
Delete a prompt

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Requires a `read_write` scope API key.

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


## list_prompt_executions

> list_prompt_executions(project_id, page, per_page, model, collection_id, country_code, language_code, prompt, from, to, mention_filter, citation_filter, competitors, output)
List prompt executions

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
**mention_filter** | Option<**String**> | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you. |  |
**citation_filter** | Option<**String**> | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). |  |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_prompts

> list_prompts(project_id, page, per_page, model, collection_id, country_code, language_code, prompt_type, brand_kind, from, to, output)
List prompts

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
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
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


## list_query_fan_outs

> list_query_fan_outs(project_id, page, per_page, view, order, direction, query, model, collection_id, country_code, language_code, prompt, prompt_type, brand_kind, range, from, to, output)
List query fan-out

The sub-queries a model actually issued when answering your tracked prompts. view=query (default) returns one row per distinct sub-query with count and share of all occurrences; view=prompt returns one row per prompt with how many distinct sub-queries it produced. Fan-out is reported mainly by ChatGPT, so an empty result usually means the models in scope do not expose it. The API returns the aggregation only: for a period-over-period delta, call it twice with explicit from/to.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**view** | Option<**String**> | Row shape: one per distinct sub-query, or one per prompt |  |[default to query]
**order** | Option<**String**> | Sort field; the allowed set depends on view |  |
**direction** | Option<**String**> |  |  |[default to desc]
**query** | Option<**String**> | Case-insensitive substring filter on the sub-query text |  |
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

