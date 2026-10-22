# SearchConsoleListResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**property** | Option<[**models::SearchConsoleProperty**](SearchConsoleProperty.md)> |  | [optional]
**from** | Option<**chrono::NaiveDate**> |  | [optional]
**to** | Option<**chrono::NaiveDate**> |  | [optional]
**data_through** | Option<**chrono::NaiveDate**> | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional]
**page** | Option<**i32**> |  | [optional]
**per_page** | Option<**i32**> |  | [optional]
**total** | Option<**i32**> | Rows in this window (one Google request, at most 25,000) | [optional]
**sort** | Option<**String**> |  | [optional]
**start_row** | Option<**i32**> | Present when start_row was set | [optional]
**truncated** | Option<**bool**> | Present (true) when Google returned 25,000 rows, so more rows exist past this window | [optional]
**data** | Option<[**Vec<models::SearchConsoleListResponseDataInner>**](SearchConsoleListResponseDataInner.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]
**properties** | Option<[**Vec<models::SearchConsoleProperty>**](SearchConsoleProperty.md)> | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional]
**excluded_properties** | Option<[**Vec<models::SearchConsoleExcludedProperty>**](SearchConsoleExcludedProperty.md)> | With a list or all, selected properties left out because another selected property already counts them | [optional]
**property_errors** | Option<[**Vec<models::SearchConsolePropertyError>**](SearchConsolePropertyError.md)> | With a list or all, selected properties Google refused, left out of the figures | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


