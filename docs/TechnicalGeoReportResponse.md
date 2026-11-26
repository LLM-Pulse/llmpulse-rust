# TechnicalGeoReportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**report_type** | **String** | The report_type requested (agent_readiness for ai_readiness) | 
**project_id** | **i32** |  | 
**batch_id** | Option<**i32**> | Bundle the report was created in; null for a report created on its own | 
**url** | Option<**String**> | The page analysed; null for the domain-level types (robots_txt, agent_readiness, llms_txt, ai_visibility) | 
**domain** | **String** |  | 
**country_code** | Option<**String**> | Set only on llms_txt and ai_visibility reports | 
**output_language_code** | Option<**String**> | ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website's own language and for every other type | 
**status** | **String** | Depends on report_type. Every type ends completed or failed; ai_visibility can also end insufficient_data | 
**result_available** | **bool** | Whether status is completed | 
**overall_score** | Option<**f64**> | Null until the report completes, and always for llms_txt | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**result_data** | Option<**std::collections::HashMap<String, serde_json::Value>**> | The full result once the report has completed; null before that. Its shape depends on report_type; an llms_txt report returns its files as LlmsTxtTechnicalGeoReport describes | 
**error_message** | Option<**String**> | Why the report failed, or why an ai_visibility report found insufficient data; null otherwise | 
**poll_after_seconds** | Option<**i32**> | Seconds to wait before polling again while the report runs; null once it has finished | 
**app_url** | Option<**String**> | Opens this report in the app | [optional]
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


