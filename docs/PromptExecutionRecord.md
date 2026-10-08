# PromptExecutionRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**prompt_id** | **i32** |  | 
**executed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Null while the answer is still pending | 
**duration_ms** | Option<**f64**> |  | 
**success** | Option<**bool**> | Null while the answer is still pending | 
**model** | **Model** |  (enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai) | 
**fan_out_queries** | Option<**Vec<String>**> | Sub-queries the model issued while answering; null when the model reports none | 
**has_mention** | **bool** |  | 
**has_citation** | **bool** |  | 
**mentions_count** | **i32** | 1 when the answer mentions the brand, otherwise 0 | 
**citations_count** | **i32** | 1 when the answer cites the brand, otherwise 0 | 
**app_url** | **String** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


