# SearchConsoleSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**property** | Option<[**models::SearchConsoleProperty**](SearchConsoleProperty.md)> |  | [optional]
**from** | Option<**chrono::NaiveDate**> |  | [optional]
**to** | Option<**chrono::NaiveDate**> |  | [optional]
**data_through** | Option<**chrono::NaiveDate**> | Latest date Google has published for the property (it lags 2-3 days). Later days are missing, not zero. | [optional]
**totals** | Option<[**models::SearchConsoleMetrics**](SearchConsoleMetrics.md)> |  | [optional]
**dimension** | Option<**String**> | Present when a breakdown was requested | [optional]
**breakdown** | Option<[**Vec<models::SearchConsoleSummaryResponseBreakdownInner>**](SearchConsoleSummaryResponseBreakdownInner.md)> | Present when a breakdown was requested, sorted by impressions descending | [optional]
**breakdown_truncated** | Option<**bool**> | Present (true) when limit or Google's 25,000-row maximum left breakdown rows out, so they add up to less than totals | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


