# AdRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | Option<**String**> | Advertising domain; null on a placement that names none (view=ads) | 
**ads** | Option<**i32**> | Placements of the domain (view=advertisers) | [optional]
**executions** | Option<**i32**> | Answers that carried them (view=advertisers) | [optional]
**prompts** | Option<**i32**> | Distinct prompts that triggered them (view=advertisers) | [optional]
**avg_position** | Option<**f64**> | Average position, 1 is the best slot; null when no placement has one (view=advertisers) | [optional]
**best_position** | Option<**i32**> | Best position, 1 is the best slot (view=advertisers) | [optional]
**id** | Option<**i32**> | The placement (view=ads) | [optional]
**model** | Option<**Model**> |  (enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview) | [optional]
**title** | Option<**String**> |  | [optional]
**snippet** | Option<**String**> |  | [optional]
**url** | Option<**String**> |  | [optional]
**position** | Option<**i32**> | Position of the placement, 1 is the best slot (view=ads) | [optional]
**is_client** | Option<**bool**> | Whether the placement is identified as your brand's own (view=ads) | [optional]
**prompt_id** | Option<**i32**> |  | [optional]
**prompt_text** | Option<**String**> |  | [optional]
**prompt_execution_id** | Option<**i32**> |  | [optional]
**executed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the answer that carried the placement was collected (view=ads) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


