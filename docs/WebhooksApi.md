# \WebhooksApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_webhook**](WebhooksApi.md#create_webhook) | **POST** /webhooks | Create a webhook subscription
[**delete_webhook**](WebhooksApi.md#delete_webhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription
[**list_webhooks**](WebhooksApi.md#list_webhooks) | **GET** /webhooks | List webhook subscriptions
[**sample_webhook_payloads**](WebhooksApi.md#sample_webhook_payloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads



## create_webhook

> models::CreateWebhook201Response create_webhook(create_webhook_request)
Create a webhook subscription

Subscribes a public HTTPS URL to a project event. LLM Pulse POSTs a JSON envelope (`event`, `occurred_at`, `project_id`, `subscription_id`, `data`) to the URL every time the event occurs, signed via the `X-LLMPulse-Signature` header (HMAC-SHA256 of the raw body computed with the subscription secret). Failed deliveries receive up to 5 attempts in total, including the first, with backoff; subscriptions auto-disable after 20 consecutive failed deliveries. While the account is below the Scale plan its subscriptions are kept but deliver nothing: no failed delivery is counted, none is disabled, and deliveries resume once the account is back on Scale or above, without resending the events from that period. Each delivery also checks that the API key that created the subscription still covers its project: an API key limited to some projects that loses the project stops the subscription for good. Idempotent for the same project + event + URL: re-posting returns the existing subscription, unless the API key or OAuth connection that created it was revoked, or that API key no longer covers the project; then it is replaced by a new subscription with a new secret. The response carries `secret` when it creates the subscription, and on a re-post only for the API key or OAuth connection that created it: any other credential gets the subscription without `secret`. Requires a `read_write` scope API key and the Scale plan or above.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_webhook_request** | [**CreateWebhookRequest**](CreateWebhookRequest.md) |  | [required] |

### Return type

[**models::CreateWebhook201Response**](createWebhook_201_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_webhook

> models::DeleteWebhook200Response delete_webhook(id)
Delete a webhook subscription

Deletes a webhook subscription; the target URL stops receiving events immediately. Requires a `read_write` scope API key. Works on every plan, with an API key created on Scale too, so a subscription paused below Scale can still be removed.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** |  | [required] |

### Return type

[**models::DeleteWebhook200Response**](deleteWebhook_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_webhooks

> models::ListWebhooks200Response list_webhooks(project_id, page, per_page)
List webhook subscriptions

Lists active webhook subscriptions for the account, optionally filtered by project. A read-only API key receives each `target_url` masked to its scheme, host and any non-default port followed by `/…`, because the full URL can let anyone post to the receiver; a `read_write` scope key receives the full URL. Works on every plan, with an API key created on Scale too. Below Scale the subscriptions are kept but deliver nothing, and they can still be listed and deleted.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | Option<**i32**> | Optional project filter |  |
**page** | Option<**i32**> |  |  |
**per_page** | Option<**i32**> | Max 100 |  |

### Return type

[**models::ListWebhooks200Response**](listWebhooks_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## sample_webhook_payloads

> models::SampleWebhookPayloads200Response sample_webhook_payloads(event_type, project_id)
Sample event payloads

Returns up to 3 example event payloads for the event type, built from the project's most recent real data (or a static sample when the project has no data). Used by integration editors such as the Zapier sample loader. Requires the Scale plan or above.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**event_type** | **String** |  | [required] |
**project_id** | **i32** |  | [required] |

### Return type

[**models::SampleWebhookPayloads200Response**](sampleWebhookPayloads_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

