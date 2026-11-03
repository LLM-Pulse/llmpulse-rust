# AiModelSentimentRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**model** | Option<**String**> | AI model key, as /dimensions/models lists it | [optional]
**label** | Option<**String**> | Display name of the model | [optional]
**color** | Option<**String**> | Hex color the app charts the model with | [optional]
**sentiments_count** | Option<**i32**> | Brand sentiment verdicts in the model's answers | [optional]
**positive_count** | Option<**i32**> | Positive and very positive verdicts | [optional]
**negative_count** | Option<**i32**> | Negative and very negative verdicts | [optional]
**net_sentiment** | Option<**f64**> | positive_count minus negative_count as a percentage (-100 to 100) of sentiments_count, neutral verdicts counted in the base; null when sentiments_count is 0 | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


