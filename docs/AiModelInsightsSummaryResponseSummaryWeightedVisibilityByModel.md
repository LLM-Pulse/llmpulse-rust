# AiModelInsightsSummaryResponseSummaryWeightedVisibilityByModel

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total_weighted_visibility_score** | Option<**f64**> | The brand's AI Visibility Score across the enabled models, its points there divided by the days with answers in any of them (the Overview's number for the same filters; a model that answered while disabled keeps its row but stays out of it); 0 when it has none | [optional]
**models** | Option<[**Vec<models::AiModelWeightedVisibilityRow>**](AiModelWeightedVisibilityRow.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


