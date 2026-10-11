# SearchConsoleRowsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**property** | Option<[**models::SearchConsoleProperty**](SearchConsoleProperty.md)> |  | [optional]
**from** | Option<**chrono::NaiveDate**> |  | [optional]
**to** | Option<**chrono::NaiveDate**> |  | [optional]
**data_through** | Option<**chrono::NaiveDate**> | Latest date Google has published for the property (it lags 2-3 days). Later days are missing, not zero. | [optional]
**page** | Option<**i32**> |  | [optional]
**per_page** | Option<**i32**> |  | [optional]
**total** | Option<**i32**> | Rows in this window (one Google request, at most 25,000) | [optional]
**sort** | Option<**String**> |  | [optional]
**start_row** | Option<**i32**> | Present when start_row was set | [optional]
**truncated** | Option<**bool**> | Present (true) when Google returned 25,000 rows, so more rows exist past this window | [optional]
**dimensions** | Option<**Vec<String>**> |  | [optional]
**data** | Option<[**Vec<models::SearchConsoleRowsResponseDataInner>**](SearchConsoleRowsResponseDataInner.md)> | One row per combination; only the requested dimensions are present | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


