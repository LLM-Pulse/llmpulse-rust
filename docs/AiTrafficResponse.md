# AiTrafficResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**provider** | **String** | The connected provider: google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo or piano | 
**from** | **chrono::NaiveDate** |  | 
**to** | **chrono::NaiveDate** |  | 
**granularity** | **Granularity** |  (enum: day, week, month) | 
**totals** | [**models::AiTrafficResponseTotals**](AiTrafficResponseTotals.md) |  | 
**by_source** | [**Vec<models::AiTrafficResponseBySourceInner>**](AiTrafficResponseBySourceInner.md) | One row per AI source with traffic in the window, most sessions first | 
**timeseries** | **std::collections::HashMap<String, std::collections::HashMap<String, i32>>** | Sessions keyed by AI source slug, then by the first day of the period (YYYY-MM-DD); a period without traffic is left out | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


