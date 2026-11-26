# AiModelInsightsReportFiltersEcho

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**from** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**to** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**granularity** | **Granularity** |  (enum: day, week, month) | 
**country_code** | Option<**String**> | Comma-separated country codes | [optional]
**language_code** | Option<**String**> | Comma-separated language codes | [optional]
**collection_id** | Option<**String**> | Comma-separated collection ids | [optional]
**prompt_type** | Option<**String**> | Comma-separated prompt types | [optional]
**brand_kind** | Option<**String**> |  | [optional]
**model** | Option<**Model**> | The model filter; always ai_overview on the AI Overview report (enum: chatgpt, ai_mode, ai_overview, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview) | [optional]
**competitors** | **Vec<i32>** | Competitor ids from the competitors parameter; empty when it was not given | 
**brand1** | Option<**String**> | Position distribution only. The id, as a string, of the competitor compared as the first brand; left out for the project brand | [optional]
**brand2** | Option<**String**> | Position distribution only. The id, as a string, of the competitor compared as the second brand, by default the competitor with the most mentions; left out when the project has none to compare | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


