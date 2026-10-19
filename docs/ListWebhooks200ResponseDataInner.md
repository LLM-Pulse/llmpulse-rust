# ListWebhooks200ResponseDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**project_id** | Option<**i32**> |  | [optional]
**event_type** | Option<**EventType**> |  (enum: mention.created, competitor_mention.created, citation.created, prompt_execution.completed, sentiment.negative_detected, recommendation.completed, intelligence_task.completed, intelligence_task.updated, geo_audit_run.completed, geo_audit_alert.triggered) | [optional]
**target_url** | Option<**String**> | The URL deliveries are sent to. A read-only API key receives only its scheme, host and any non-default port followed by `/…` (for example `https://hook.eu1.make.com/…`); a `read_write` scope key receives the full URL. | [optional]
**disabled** | Option<**bool**> | True when the subscription receives no more events, including when the API key or OAuth connection that created it was revoked, or when that API key is limited to some projects and no longer covers the subscription's project. Creating it again with the same project, event and URL replaces it with a new subscription and secret. | [optional]
**failure_count** | Option<**i32**> |  | [optional]
**last_delivered_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


