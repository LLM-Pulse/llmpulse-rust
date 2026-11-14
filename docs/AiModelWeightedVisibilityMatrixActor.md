# AiModelWeightedVisibilityMatrixActor

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | Option<**Type**> |  (enum: project, competitor) | [optional]
**id** | Option<**i32**> | Project id, or competitor id | [optional]
**competitor_id** | Option<**i32**> | Null for the project, the competitor id otherwise | [optional]
**name** | Option<**String**> |  | [optional]
**domain** | Option<**String**> | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional]
**total_weighted_visibility_score** | Option<**f64**> | The actor's AI Visibility Score across the enabled models, its points there divided by the project's days with answers in them, so actors compare | [optional]
**models** | Option<[**std::collections::HashMap<String, models::AiModelWeightedVisibilityCell>**](AiModelWeightedVisibilityCell.md)> | One cell per model, keyed by model | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


