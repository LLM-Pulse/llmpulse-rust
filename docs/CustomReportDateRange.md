# CustomReportDateRange

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | rolling (the last range_days days), previous_month (the previous calendar month), previous_3_months (the 3 calendar months before the current one) or custom (fixed dates, custom_from to custom_to) (enum: rolling, previous_month, previous_3_months, custom) | 
**range_days** | Option<**i32**> | Length of a rolling window; null for the other types | 
**custom_from** | Option<**chrono::NaiveDate**> | First day chosen for a custom range; null for the other types | 
**custom_to** | Option<**chrono::NaiveDate**> | Last day chosen for a custom range, which can be after today; null for the other types | 
**from** | Option<**chrono::NaiveDate**> | First day of the window as of now (detail only) | [optional]
**to** | Option<**chrono::NaiveDate**> | Last day of the window as of now (detail only); a custom range stops at today | [optional]
**label** | Option<**String**> | The window as the report shows it (detail only) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


