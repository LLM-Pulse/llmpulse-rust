# QueryWebAnalyticsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**query** | Option<**serde_json::Value**> | The query in the provider's native format (see GET /web_analytics/schema): a JSON object for GA4, Adobe, Matomo, Plausible and Piano; for PostHog, {\"query\": \"<HogQL>\"} or the HogQL string. Deliberately untyped so generated clients accept either shape. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


