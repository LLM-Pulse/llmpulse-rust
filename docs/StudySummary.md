# StudySummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**title** | **String** |  | 
**study_type** | **String** | brand_set, sector, geo, topic or custom | 
**cadence** | **String** | one_shot or monthly | 
**status** | **String** | active or archived | 
**project_id** | Option<**i32**> | The project the study is attached to; null for an account-level study | 
**subjects_count** | **i32** |  | 
**ai_models** | **Vec<AiModels>** | Analyst models the study runs on (enum: chatgpt, perplexity, gemini, deepseek, grok, claude) | 
**output_language_code** | **String** | ISO 639-1 code of the language the reports are written in | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**last_report_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the latest report started; null before the first one | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


