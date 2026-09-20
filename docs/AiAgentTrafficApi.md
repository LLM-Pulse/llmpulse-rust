# \AiAgentTrafficApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_agent_traffic**](AiAgentTrafficApi.md#get_agent_traffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta)
[**get_ai_traffic**](AiAgentTrafficApi.md#get_ai_traffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above)
[**list_agent_bots**](AiAgentTrafficApi.md#list_agent_bots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above)



## get_agent_traffic

> models::AgentTrafficResponse get_agent_traffic(project_id, range, from, to, bot, company, group_by, granularity)
AI bot crawler traffic (Scale plan or above, Beta)

Aggregated AI bot traffic hitting the project's origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**bot** | Option<**String**> | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) |  |
**company** | Option<**String**> | Filter by company (e.g. openai, anthropic, google) |  |
**group_by** | Option<**String**> |  |  |[default to bot]
**granularity** | Option<**String**> |  |  |

### Return type

[**models::AgentTrafficResponse**](AgentTrafficResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_ai_traffic

> get_ai_traffic(project_id, range, from, to, source, granularity)
AI referral traffic (Scale plan or above)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**source** | Option<**String**> | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) |  |
**granularity** | Option<**String**> |  |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_agent_bots

> models::AgentBotsResponse list_agent_bots(project_id, output)
AI bot catalog (Scale plan or above)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on the Scale plan or above.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::AgentBotsResponse**](AgentBotsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

