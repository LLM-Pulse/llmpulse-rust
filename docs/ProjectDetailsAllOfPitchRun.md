# ProjectDetailsAllOfPitchRun

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | Option<**Status**> | starting before the run begins, running while answers arrive, ready once every AI model has answered or stopped trying (enum: starting, running, ready) | [optional]
**launched_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**settled_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**models** | Option<**Vec<Models>**> | The AI models the run asks, fixed when it starts (enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode) | [optional]
**answers_expected** | Option<**i32**> |  | [optional]
**answers_received** | Option<**i32**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


