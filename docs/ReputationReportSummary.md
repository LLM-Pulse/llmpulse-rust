# ReputationReportSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **String** | Report id for GET /reputation/reports/{id} | 
**status** | **Status** |  (enum: pending, processing, completed, failed) | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**processed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**available_models** | **Vec<AvailableModels>** | Analyst models that produced data (enum: chatgpt, perplexity, gemini, deepseek, grok, claude) | 
**missing_models** | **Vec<MissingModels>** | Analyst models with no data yet (enum: chatgpt, perplexity, gemini, deepseek, grok, claude) | 
**error_message** | Option<**String**> | Why the report failed; null unless status is failed | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


