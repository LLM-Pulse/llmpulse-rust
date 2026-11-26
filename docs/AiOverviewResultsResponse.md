# AiOverviewResultsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**from** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**to** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**filters** | [**models::AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  | 
**granularity** | **Granularity** |  (enum: day, week, month) | 
**summary** | [**models::AiOverviewResultCounts**](AiOverviewResultCounts.md) |  | 
**chart** | [**Vec<models::AiOverviewResultsResponseChartInner>**](AiOverviewResultsResponseChartInner.md) | One point per period of the window, oldest first, 0 included | 
**by_prompt** | [**models::AiOverviewResultsResponseByPrompt**](AiOverviewResultsResponseByPrompt.md) |  | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


