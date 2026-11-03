# AiModelInsightsSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**filters** | Option<[**models::AiModelInsightsFiltersEcho**](AiModelInsightsFiltersEcho.md)> |  | [optional]
**models** | Option<[**Vec<models::AiModelInsightsModel>**](AiModelInsightsModel.md)> | The AI models the account has enabled or that answered in the window, in the in-app column order | [optional]
**summary** | Option<[**models::AiModelInsightsSummaryResponseSummary**](AiModelInsightsSummaryResponseSummary.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


