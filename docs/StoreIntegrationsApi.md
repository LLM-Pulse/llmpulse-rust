# \StoreIntegrationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**accept_catalog_prompt_suggestions**](StoreIntegrationsApi.md#accept_catalog_prompt_suggestions) | **POST** /catalog_prompt_suggestions/accept | Accept catalog prompt suggestions
[**create_catalog_prompt_suggestions**](StoreIntegrationsApi.md#create_catalog_prompt_suggestions) | **POST** /catalog_prompt_suggestions | Suggest buyer prompts from catalog products
[**get_store_connection**](StoreIntegrationsApi.md#get_store_connection) | **GET** /store_connection | Match a store to a project
[**list_ai_orders**](StoreIntegrationsApi.md#list_ai_orders) | **GET** /ai_orders | Read AI-referred store orders
[**list_catalog_prompt_suggestions**](StoreIntegrationsApi.md#list_catalog_prompt_suggestions) | **GET** /catalog_prompt_suggestions | List catalog prompt suggestions
[**reject_catalog_prompt_suggestions**](StoreIntegrationsApi.md#reject_catalog_prompt_suggestions) | **POST** /catalog_prompt_suggestions/reject | Reject catalog prompt suggestions
[**replace_ai_orders**](StoreIntegrationsApi.md#replace_ai_orders) | **PUT** /ai_orders | Replace AI-referred store orders for a window



## accept_catalog_prompt_suggestions

> models::CatalogPromptSuggestionsAcceptResponse accept_catalog_prompt_suggestions(catalog_prompt_suggestion_ids_request)
Accept catalog prompt suggestions

Starts tracking pending suggestions: each one becomes a prompt, tagged with a collection named after its product. Suggestions that are no longer pending come back in skipped. All accepted suggestions must share one country and language. When the new prompts would exceed the plan, the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a `read_write` scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**catalog_prompt_suggestion_ids_request** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md) |  | [required] |

### Return type

[**models::CatalogPromptSuggestionsAcceptResponse**](CatalogPromptSuggestionsAcceptResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_catalog_prompt_suggestions

> models::CatalogPromptSuggestionsCreateResponse create_catalog_prompt_suggestions(catalog_prompt_suggestions_create_request)
Suggest buyer prompts from catalog products

Writes buyer prompts for up to 20 catalog products and saves them as pending suggestions in the project's Suggested prompts queue, with the product recorded on each. Generation draws on the hourly prompt-suggestion allowance the app also uses (ERR_QUOTA_EXCEEDED once it is used up); a failed generation returns ERR_GENERATION_FAILED (502) and can be retried. Requires a `read_write` scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**catalog_prompt_suggestions_create_request** | [**CatalogPromptSuggestionsCreateRequest**](CatalogPromptSuggestionsCreateRequest.md) |  | [required] |

### Return type

[**models::CatalogPromptSuggestionsCreateResponse**](CatalogPromptSuggestionsCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_store_connection

> models::StoreConnectionResponse get_store_connection(platform, domain)
Match a store to a project

Tells a store app whether the API key's account can use it and which project the store belongs to: the live project whose domain equals the store domain, else one whose domain is a parent or a subdomain of it, else null. candidates lists every live project of the account so the app can offer a picker. Takes no project_id. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**platform** | **String** | Store platform | [required] |
**domain** | **String** | Store domain, with or without scheme, e.g. acme-store.com | [required] |

### Return type

[**models::StoreConnectionResponse**](StoreConnectionResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_ai_orders

> models::AiOrdersResponse list_ai_orders(project_id, platform, from, to)
Read AI-referred store orders

Reads back the AI-referred orders a store app pushed for a project: totals, one row per AI assistant and a daily series of the days with orders. Revenue values are decimal strings in currency. Team members need read access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**platform** | Option<**String**> | Store platform |  |[default to shopify]
**from** | Option<**chrono::NaiveDate**> | First day (YYYY-MM-DD). Defaults to 89 days before to |  |
**to** | Option<**chrono::NaiveDate**> | Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days |  |

### Return type

[**models::AiOrdersResponse**](AiOrdersResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_catalog_prompt_suggestions

> models::CatalogPromptSuggestionsResponse list_catalog_prompt_suggestions(project_id, status, product_external_id, page, per_page)
List catalog prompt suggestions

Lists the buyer prompts suggested from a store catalog, oldest first, with their status and the product each one came from. Team members need read access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**status** | Option<**String**> | Only suggestions in this status |  |
**product_external_id** | Option<**String**> | Only suggestions for this store product id |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 50]

### Return type

[**models::CatalogPromptSuggestionsResponse**](CatalogPromptSuggestionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## reject_catalog_prompt_suggestions

> models::CatalogPromptSuggestionsRejectResponse reject_catalog_prompt_suggestions(catalog_prompt_suggestion_ids_request)
Reject catalog prompt suggestions

Marks pending suggestions as rejected; suggestions that are no longer pending stay as they are. Requires a `read_write` scope API key and, for team members, update access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**catalog_prompt_suggestion_ids_request** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md) |  | [required] |

### Return type

[**models::CatalogPromptSuggestionsRejectResponse**](CatalogPromptSuggestionsRejectResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## replace_ai_orders

> models::AiOrdersUpdateResponse replace_ai_orders(ai_orders_update_request)
Replace AI-referred store orders for a window

Replaces the daily AI-referred orders and revenue of the from..to window. Send the raw referring host or utm_source of each order's first visit as referrer: LLM Pulse classifies it and ignores anything that is not an AI assistant. Entries for the same day and assistant are summed. Every stored row of that project and platform inside the window is replaced, so pushing the same window again converges instead of counting twice. Rows are kept per project and platform, not per store, so one store reports per project. Requires a `read_write` scope API key and, for team members, update access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**ai_orders_update_request** | [**AiOrdersUpdateRequest**](AiOrdersUpdateRequest.md) |  | [required] |

### Return type

[**models::AiOrdersUpdateResponse**](AiOrdersUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

