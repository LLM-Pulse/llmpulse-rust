# AiModelPositionDistributionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**from** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**to** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**filters** | [**models::AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  | 
**granularity** | **Granularity** |  (enum: day, week, month) | 
**brands** | [**Vec<models::AiModelPositionDistributionBrand>**](AiModelPositionDistributionBrand.md) | The first brand (brand1, else the project) and the second (brand2, else the competitor with the most mentions, else the project), each left out when it has no mention in the window | 
**max_stacked_value** | **i32** | The largest mentions count of one period across the brands, for a shared chart axis | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


