# AiModelSentimentCell

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**value** | Option<**f64**> | The actor's net sentiment in the model, positive_count minus negative_count as a percentage (-100 to 100) of total_sentiments; null when total_sentiments is 0 | [optional]
**total_sentiments** | Option<**i32**> | The actor's sentiment verdicts in the model's answers | [optional]
**positive_count** | Option<**i32**> | Positive and very positive verdicts | [optional]
**negative_count** | Option<**i32**> | Negative and very negative verdicts | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


