# SearchConsoleDecayResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**property** | Option<[**models::SearchConsoleProperty**](SearchConsoleProperty.md)> |  | [optional]
**properties** | Option<[**Vec<models::SearchConsoleProperty>**](SearchConsoleProperty.md)> | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional]
**excluded_properties** | Option<[**Vec<models::SearchConsoleExcludedProperty>**](SearchConsoleExcludedProperty.md)> | With a list or all, selected properties left out because another selected property already counts them | [optional]
**property_errors** | Option<[**Vec<models::SearchConsolePropertyError>**](SearchConsolePropertyError.md)> | With a list or all, selected properties Google refused, left out of the figures | [optional]
**from** | Option<**chrono::NaiveDate**> |  | [optional]
**to** | Option<**chrono::NaiveDate**> |  | [optional]
**data_through** | Option<**chrono::NaiveDate**> | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional]
**dimension** | Option<**Dimension**> |  (enum: page, query) | [optional]
**compared_through** | Option<**chrono::NaiveDate**> | Last day of the requested window that is compared, to or the last day Google has published when that is earlier | [optional]
**previous_from** | Option<**chrono::NaiveDate**> | Start of the window compared against, the same length as from..compared_through and just before it | [optional]
**previous_to** | Option<**chrono::NaiveDate**> |  | [optional]
**min_clicks** | Option<**i32**> |  | [optional]
**page** | Option<**i32**> |  | [optional]
**per_page** | Option<**i32**> |  | [optional]
**total** | Option<**i32**> | Rows in the report before paging | [optional]
**truncated** | Option<**bool**> | Present (true) when Google returned its 25,000-row maximum for a property, so the report covers its top rows only | [optional]
**data** | Option<[**Vec<models::SearchConsoleDecayResponseDataInner>**](SearchConsoleDecayResponseDataInner.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


