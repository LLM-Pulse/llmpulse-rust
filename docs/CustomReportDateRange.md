# CustomReportDateRange

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | rolling (the last range_days days) or previous_month (the previous calendar month) (enum: rolling, previous_month) | 
**range_days** | Option<**i32**> | Length of a rolling window; null for previous_month | 
**from** | Option<**chrono::NaiveDate**> | First day of the window as of now (detail only) | [optional]
**to** | Option<**chrono::NaiveDate**> | Last day of the window as of now (detail only) | [optional]
**label** | Option<**String**> | The window as the report shows it (detail only) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


