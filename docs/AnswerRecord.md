# AnswerRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**prompt_id** | **i32** |  | 
**prompt_text** | **String** |  | 
**model** | **Model** |  (enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview) | 
**executed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**duration_ms** | Option<**f64**> | Milliseconds our pipeline spent processing the collected answer, rounded to one decimal place | 
**no_result** | **bool** | True for a sentinel non-answer (no answer could be collected after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics | 
**no_result_reason** | Option<**NoResultReason**> | Present only when no_result is true. declined = the model declined to answer and response holds its reply; no_answer = no answer could be collected (enum: declined, no_answer) | [optional]
**mentions_count** | **i32** | Mentions of your brand in the answer | 
**citations_count** | **i32** | Citations of your brand in the answer | 
**app_url** | **String** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project | 
**response** | Option<**String**> | The answer text, cut to 10,000 characters (without query) | [optional]
**response_truncated** | Option<**bool**> | Whether response was cut (without query) | [optional]
**snippet** | Option<**String**> | The text around the first match (with query) | [optional]
**match_count** | Option<**i32**> | Matches of query in the answer (with query) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


