# AiModelSentimentMatrixActor

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | Option<**Type**> |  (enum: project, competitor) | [optional]
**id** | Option<**i32**> | Project id, or competitor id | [optional]
**competitor_id** | Option<**i32**> | Null for the project, the competitor id otherwise | [optional]
**name** | Option<**String**> |  | [optional]
**domain** | Option<**String**> | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional]
**total_sentiments** | Option<**i32**> | The actor's sentiment verdicts summed over the models | [optional]
**models** | Option<[**std::collections::HashMap<String, models::AiModelSentimentCell>**](AiModelSentimentCell.md)> | One cell per model, keyed by model | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


