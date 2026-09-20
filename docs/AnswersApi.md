# \AnswersApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_answer**](AnswersApi.md#get_answer) | **GET** /answers/{id} | Get one AI response
[**list_answers**](AnswersApi.md#list_answers) | **GET** /answers | List AI responses



## get_answer

> models::AnswerDetails get_answer(project_id, id, include_source_page_details)
Get one AI response

Full answer with mentions, citations, sentiments, sources, shopping_products, brand_entities, fan_out_queries. Pass `include_source_page_details=true` to nest page-cache metadata under each source.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**id** | **i32** |  | [required] |
**include_source_page_details** | Option<**bool**> |  |  |[default to false]

### Return type

[**models::AnswerDetails**](AnswerDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_answers

> list_answers(project_id, model, collection_id, country_code, language_code, prompt, mention_filter, citation_filter, competitors, from, to, page, per_page, query, no_result)
List AI responses

Successful prompt-execution responses with truncated content (max 10,000 chars). Pass `query` for case-insensitive full-text search inside response texts: `total` becomes the exact count of matching responses and each item returns `snippet` + `match_count` instead of `response`/`response_truncated`.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**model** | Option<**String**> | Filter by AI model. Models the API key's user has not enabled are silently dropped. |  |
**collection_id** | Option<[**GetTimeseriesCollectionIdParameter**](GetTimeseriesCollectionIdParameter.md)> | One collection/tag ID or a comma-separated list of IDs |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**i32**> | Filter by prompt ID |  |
**mention_filter** | Option<**String**> | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you. |  |
**citation_filter** | Option<**String**> | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). |  |
**competitors** | Option<**String**> | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**query** | Option<**String**> | Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode. |  |
**no_result** | Option<**bool**> | Filter sentinel non-answers (provider returned nothing after retries; excluded from platform metrics). false = only real answers, true = only sentinels, omit = both. Every item carries its own no_result flag. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

