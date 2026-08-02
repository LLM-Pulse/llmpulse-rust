# CreateWebhook201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**project_id** | Option<**i32**> |  | [optional]
**event_type** | Option<**EventType**> |  (enum: mention.created, competitor_mention.created, citation.created, prompt_execution.completed, sentiment.negative_detected, recommendation.completed, intelligence_task.completed) | [optional]
**target_url** | Option<**String**> |  | [optional]
**disabled** | Option<**bool**> |  | [optional]
**failure_count** | Option<**i32**> |  | [optional]
**last_delivered_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**secret** | Option<**String**> | HMAC signing secret (whsec_...). Only returned on create. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


