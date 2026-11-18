# AiModelDeclinedAnswersResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**from** | **chrono::DateTime<chrono::FixedOffset>** | Start of the tracking period holding the first day asked for | 
**to** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**model** | **Model** | The model the counts are for (enum: gemini) | 
**cadence** | **String** | The account's current tracking cadence: daily, weekly or monthly. Chart periods before a switch from weekly to daily stay weekly. | 
**filters** | Option<[**models::AiModelDeclinedAnswersResponseFilters**](AiModelDeclinedAnswersResponseFilters.md)> |  | [optional]
**summary** | [**models::AiModelDeclinedAnswersResponseSummary**](AiModelDeclinedAnswersResponseSummary.md) |  | 
**chart** | [**Vec<models::AiModelDeclinedAnswersResponseChartInner>**](AiModelDeclinedAnswersResponseChartInner.md) | One point per tracking period holding an answer, oldest first. A period without answers has no point; a period with answers and no declines is a real 0. | 
**by_prompt** | [**models::AiModelDeclinedAnswersResponseByPrompt**](AiModelDeclinedAnswersResponseByPrompt.md) |  | 
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


