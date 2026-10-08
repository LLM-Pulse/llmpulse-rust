# SentimentRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**prompt_execution_id** | **i32** |  | 
**prompt_text** | **String** |  | 
**model** | **Model** |  (enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai) | 
**analysis** | **Analysis** |  (enum: very_positive, positive, neutral, negative, very_negative) | 
**score** | Option<**f64**> | From -1 (very negative) to 1 (very positive) | 
**comment** | Option<**String**> |  | 
**topics** | Option<**String**> | Comma-separated topics | 
**competitor_id** | Option<**i32**> | Null for a sentiment about the project's own brand | 
**competitor_name** | Option<**String**> | Null for a sentiment about the project's own brand | 
**is_brand_sentiment** | **bool** |  | 
**executed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


