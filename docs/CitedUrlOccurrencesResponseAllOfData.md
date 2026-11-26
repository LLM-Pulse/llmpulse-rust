# CitedUrlOccurrencesResponseAllOfData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source_id** | **i32** |  | 
**answer_id** | **i32** |  | 
**prompt_execution_id** | **i32** | Same as answer_id | 
**prompt_id** | **i32** |  | 
**prompt_text** | **String** |  | 
**model** | **Model** |  (enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview) | 
**executed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**citation_position** | **i32** | Rank of the citation in the answer; 0 for a background source reference | 
**url** | **String** | Normalized cited URL | 
**domain** | Option<**String**> |  | 
**source_type** | **String** | owned, competitor or third_party | 
**response_excerpt** | **String** | The first 600 characters of the answer | 
**response_truncated** | **bool** |  | 
**fan_out_queries** | Option<**Vec<String>**> | Sub-queries the model issued while answering; null when the model reports none | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


