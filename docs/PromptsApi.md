# \PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**accept_suggested_prompts**](PromptsApi.md#accept_suggested_prompts) | **POST** /suggested_prompts/accept | Accept suggested prompts
[**create_prompt_generation**](PromptsApi.md#create_prompt_generation) | **POST** /prompt_generations | Generate prompt suggestions
[**create_prompts**](PromptsApi.md#create_prompts) | **POST** /prompts | Bulk-create prompts
[**delete_prompt**](PromptsApi.md#delete_prompt) | **DELETE** /prompts/{id} | Delete a prompt
[**get_prompt_generation**](PromptsApi.md#get_prompt_generation) | **GET** /prompt_generations/{id} | Get a prompt generation run
[**import_prompts**](PromptsApi.md#import_prompts) | **POST** /prompts/import | Import prompts
[**list_prompt_executions**](PromptsApi.md#list_prompt_executions) | **GET** /dimensions/prompt_executions | List prompt executions
[**list_prompts**](PromptsApi.md#list_prompts) | **GET** /dimensions/prompts | List prompts
[**list_query_fan_outs**](PromptsApi.md#list_query_fan_outs) | **GET** /dimensions/query_fan_outs | List query fan-out
[**list_suggested_prompts**](PromptsApi.md#list_suggested_prompts) | **GET** /suggested_prompts | List suggested prompts
[**reject_suggested_prompts**](PromptsApi.md#reject_suggested_prompts) | **POST** /suggested_prompts/reject | Reject suggested prompts
[**update_prompt**](PromptsApi.md#update_prompt) | **PATCH** /prompts/{id} | Edit a prompt's categorization



## accept_suggested_prompts

> models::SuggestedPromptsAcceptResponse accept_suggested_prompts(suggested_prompts_accept_request)
Accept suggested prompts

Starts tracking up to 100 pending suggestions: each becomes a prompt in its own country and language, optionally put in one tag (tag_ids or tag_names; create_missing creates a missing name when the team member may create tags). Suggestions that are no longer pending come back in skipped. When the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and accepts nothing. The prompts of a launched pitch project are fixed, so accepting a suggestion returns ERR_INVALID_PARAM with error.meta.reason pitch_prompts_frozen. Requires a `read_write` scope API key and, for team members, create access to Prompts.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**suggested_prompts_accept_request** | [**SuggestedPromptsAcceptRequest**](SuggestedPromptsAcceptRequest.md) |  | [required] |

### Return type

[**models::SuggestedPromptsAcceptResponse**](SuggestedPromptsAcceptResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_prompt_generation

> models::PromptGenerationResponse create_prompt_generation(prompt_generation_request)
Generate prompt suggestions

Starts a suggestion run with one of the generators behind the app's Add prompts wizards and answers 202 with the run. website writes suggestions from the scraped website (80% non-brand, 20% brand; up to 100 per project, then ERR_LIMIT_REACHED), keyword from a keyword or the project profile (optionally around a competitor), topic from a topic, reddit from Reddit discussions of a topic or brand, paa from Google People Also Ask (up to 5 keywords, counted against the account's 24-hour lookup allowance), reputational from brand reputation questions, translate from the project's prompts of another locale, search_console from the connected property's top queries of the last 28 days (Growth plan or above, ERR_PLAN_REQUIRED). The suggestions land in the Suggested prompts queue; poll GET /prompt_generations/{id}, then accept the ones you want with POST /suggested_prompts/accept. Nothing is tracked until accepted. The request is validated before the run starts, and refused with ERR_LIMIT_REACHED when the plan has no prompt slot left, ERR_INVALID_PARAM with error.meta.reason pitch_prompts_frozen for a launched pitch project, whose prompts are fixed, or ERR_QUOTA_EXCEEDED after 60 runs in an hour (the per-user prompt suggestion allowance, shared with project setup). Requires a `read_write` scope API key and, for team members, create access to Prompts.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**prompt_generation_request** | [**PromptGenerationRequest**](PromptGenerationRequest.md) |  | [required] |

### Return type

[**models::PromptGenerationResponse**](PromptGenerationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_prompts

> models::PromptsCreateResponse create_prompts(prompts_create_request)
Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. When the project does not run on the schedule (paused, or beyond the plan's project limit) the prompts are still created, and the response says so with `tracked` false, `untracked_reason` and a `warning`. New prompts get their first answers within about 24 hours. The first run is queued on creation and a nightly run at 00:00 Europe/Madrid picks up any prompt still without answers, as far as the account's allowance of AI answers for the cycle covers it. When the allowance left cannot give every new prompt one answer per enabled AI model, `first_runs_wait_until` gives the reset time when the rest run, with a `warning`. On an account that caps each project's executions at its prompt limit, the project's own share of the allowance counts the same way. A pitch project holds at most 100 prompts in all, deleted ones included (ERR_LIMIT_REACHED past that), and the prompts of a launched pitch project are fixed, so adding one returns ERR_INVALID_PARAM with error.meta.reason pitch_prompts_frozen. Requires a `read_write` scope API key.

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

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Until that job finishes, its answers, mentions and metrics still count the prompt, so totals can include it for a short while. The prompts of a launched pitch project are fixed, so deleting one returns ERR_INVALID_PARAM with error.meta.reason pitch_prompts_frozen. Requires a `read_write` scope API key.

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


## get_prompt_generation

> models::PromptGenerationResponse get_prompt_generation(project_id, id)
Get a prompt generation run

Returns a run started with POST /prompt_generations: processing while the generator works, then completed with the suggestions it saved to the Suggested prompts queue, or failed with an error code and message. Poll every few seconds; most runs finish within a minute. Runs are kept for 24 hours, their suggestions stay in the queue.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::PromptGenerationResponse**](PromptGenerationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## import_prompts

> models::PromptsImportResponse import_prompts(prompts_import_request)
Import prompts

The app's CSV import as JSON: up to 500 rows, each with its own prompt, country_code, language_code (codes or names; both default to the project's) and tags, created when missing. Duplicates are skipped and existing prompts still get the row's tags. The prompt limits are checked before anything is written: when the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and imports nothing. A row is skipped and comes back in row_errors when its country or language is unknown, when it would give a prompt more than 50 tags (rows repeating a prompt add up) or when its tags would take the request past 500 new tags. For a team member without create access to Tags, a row that needs a tag that does not exist yet is skipped and comes back in row_errors. For a team member without update access to Prompts, a row matching a prompt that already existed adds no tags to it, and comes back in row_errors when it would have added one. Responds 201 when it created prompts, 200 otherwise. The prompts of a launched pitch project are fixed, so importing one returns ERR_INVALID_PARAM with error.meta.reason pitch_prompts_frozen. `tracked` false, with `untracked_reason` and a `warning`, means the project does not run on the schedule, so the imported prompts do not run until that changes. Imported prompts get their first answers within about 24 hours. The first run is queued on creation and a nightly run at 00:00 Europe/Madrid picks up any prompt still without answers, as far as the account's allowance of AI answers for the cycle covers it. When the allowance left cannot give every new prompt one answer per enabled AI model, `first_runs_wait_until` gives the reset time when the rest run, with a `warning`. On an account that caps each project's executions at its prompt limit, the project's own share of the allowance counts the same way. Requires a `read_write` scope API key and, for team members, create access to Prompts.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**prompts_import_request** | [**PromptsImportRequest**](PromptsImportRequest.md) |  | [required] |

### Return type

[**models::PromptsImportResponse**](PromptsImportResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_prompt_executions

> models::PromptExecutionsResponse list_prompt_executions(project_id, page, per_page, model, collection_id, country_code, language_code, prompt, from, to, mention_filter, citation_filter, competitors, output, prompt_type, brand_kind)
List prompt executions

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**u32**> | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. |  |
**mention_filter** | Option<**String**> | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space; on answers, finished answers only). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you. |  |
**citation_filter** | Option<**String**> | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it (cites_no_brands still allows other domains), plus no_citations, finished answers that cite no source at all. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). |  |
**competitors** | Option<**String**> | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |

### Return type

[**models::PromptExecutionsResponse**](PromptExecutionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_prompts

> models::PromptsResponse list_prompts(project_id, page, per_page, model, collection_id, country_code, language_code, prompt, prompt_type, brand_kind, from, to, output)
List prompts

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**model** | Option<**String**> | Keep only the prompts with at least one execution on this AI model, of any outcome and date (the prompts /dimensions/prompt_executions lists for the same model). Prompts have no model of their own, so a prompt with no execution on this model yet (a newly enabled model, or a locale the model does not cover) is left out. An unknown value, or a model the API key's user has not enabled, returns 422 ERR_INVALID_PARAM. from and to still filter prompt creation. |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**u32**> | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::PromptsResponse**](PromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

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
**model** | Option<**String**> | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**prompt** | Option<**u32**> | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. |  |
**prompt_type** | Option<**String**> | One prompt type or a comma-separated list: informational, navigational, commercial, transactional |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_suggested_prompts

> models::SuggestedPromptsResponse list_suggested_prompts(project_id, source, status, page, per_page)
List suggested prompts

Lists the project's Suggested prompts queue, the same list the app's Suggested Prompts tab shows, oldest first. It holds the suggestions of every generator (website, magic for keyword runs, topic, reddit, paa, reputational, translate, gsc for Search Console, catalog). Pending suggestions by default; status=all also returns accepted (with the prompt they became) and rejected ones. Team members need create access to Prompts, like the app's tab.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**source** | Option<**String**> | Only suggestions from this generator |  |
**status** | Option<**String**> | Only suggestions in this status |  |[default to pending]
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 50]

### Return type

[**models::SuggestedPromptsResponse**](SuggestedPromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## reject_suggested_prompts

> models::SuggestedPromptsRejectResponse reject_suggested_prompts(suggested_prompt_ids_request)
Reject suggested prompts

Marks up to 100 pending suggestions as rejected, so they leave the pending list; suggestions that are no longer pending stay as they are. Tracks and deletes nothing. Requires a `read_write` scope API key and, for team members, create access to Prompts.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**suggested_prompt_ids_request** | [**SuggestedPromptIdsRequest**](SuggestedPromptIdsRequest.md) |  | [required] |

### Return type

[**models::SuggestedPromptsRejectResponse**](SuggestedPromptsRejectResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_prompt

> models::PromptCategorizationResponse update_prompt(id, update_prompt_request)
Edit a prompt's categorization

Manual categorization, exactly like editing the intent and brand badges on the prompt page: send `prompt_type`, `brand_kind` or both. The prompt is marked as manually categorized (`categorization_source` becomes `manual`), so automatic categorization no longer changes it; the prompt page can revert it to automatic. Any other field returns ERR_INVALID_PARAM. Not available from a white-label portal (ERR_INTEGRATION_UNAVAILABLE), where the page hides the editor. Requires a `read_write` scope API key and, for team members, update permission on Prompts.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** |  | [required] |
**update_prompt_request** | [**UpdatePromptRequest**](UpdatePromptRequest.md) |  | [required] |

### Return type

[**models::PromptCategorizationResponse**](PromptCategorizationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

