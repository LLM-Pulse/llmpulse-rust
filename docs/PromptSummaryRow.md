# PromptSummaryRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**prompt_id** | Option<**i32**> |  | [optional]
**prompt_text** | Option<**String**> |  | [optional]
**model** | Option<**String**> | Only present when breakdown=model | [optional]
**responses** | Option<**i32**> |  | [optional]
**mentions** | Option<**i32**> |  | [optional]
**citations** | Option<**i32**> |  | [optional]
**visibility** | Option<**f64**> |  | [optional]
**mention_rate** | Option<**f64**> |  | [optional]
**citation_rate** | Option<**f64**> |  | [optional]
**avg_mention_position** | Option<**f64**> |  | [optional]
**avg_position** | Option<**f64**> |  | [optional]
**app_url** | Option<**String**> | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project | [optional]
**country_code** | Option<**String**> | Country of the prompt, as in /dimensions/prompts | [optional]
**language_code** | Option<**String**> | Language of the prompt, as in /dimensions/prompts | [optional]
**prompt_type** | Option<**String**> | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified | [optional]
**brand_kind** | Option<**String**> | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified | [optional]
**tags** | Option<[**Vec<models::TagRef>**](TagRef.md)> | Every tag the prompt belongs to | [optional]
**sentiment_responses** | Option<**i32**> | Responses in the window with a sentiment verdict for the brand, the base of the sentiment percentages (deduplicated like the sentiment timeseries) | [optional]
**sentiment_very_positive** | Option<**f64**> | Percentage (0-100) of sentiment_responses whose brand verdict is very positive; null when sentiment_responses is 0 | [optional]
**sentiment_positive** | Option<**f64**> | Percentage (0-100) of sentiment_responses whose brand verdict is positive; null when sentiment_responses is 0 | [optional]
**sentiment_neutral** | Option<**f64**> | Percentage (0-100) of sentiment_responses whose brand verdict is neutral; null when sentiment_responses is 0 | [optional]
**sentiment_negative** | Option<**f64**> | Percentage (0-100) of sentiment_responses whose brand verdict is negative; null when sentiment_responses is 0 | [optional]
**sentiment_very_negative** | Option<**f64**> | Percentage (0-100) of sentiment_responses whose brand verdict is very negative; null when sentiment_responses is 0 | [optional]
**net_sentiment** | Option<**f64**> | Positive minus negative percentages (-100 to 100), neutral counted in the base; null when sentiment_responses is 0 | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


