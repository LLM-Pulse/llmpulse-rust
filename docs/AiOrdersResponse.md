# AiOrdersResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**platform** | **String** |  | 
**currency** | Option<**String**> | ISO 4217 code of the most recent stored day; null when the window holds no stored order | 
**from** | **chrono::NaiveDate** |  | 
**to** | **chrono::NaiveDate** |  | 
**totals** | [**models::AiOrdersResponseTotals**](AiOrdersResponseTotals.md) |  | 
**by_source** | [**Vec<models::AiOrdersResponseBySourceInner>**](AiOrdersResponseBySourceInner.md) | One row per AI assistant, highest revenue first | 
**series** | [**Vec<models::AiOrdersResponseSeriesInner>**](AiOrdersResponseSeriesInner.md) | Days that have stored orders, oldest first | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


