# CitationSeries

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**granularity** | **Granularity** |  (enum: day, week, month) | 
**total** | **i32** | Equal to total_responses | 
**by_model** | **std::collections::HashMap<String, i32>** | Answers per AI model, keyed by model, largest first | 
**data** | [**Vec<models::AiModelPositionDistributionBrandBucketsInnerDataInner>**](AiModelPositionDistributionBrandBucketsInnerDataInner.md) | One point per period holding a filtered answer, oldest first; a zero means answers ran and none cited it | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


