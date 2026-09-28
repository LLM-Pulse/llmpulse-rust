# TimeseriesPoint

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | Option<**chrono::NaiveDate**> | Calendar day in Europe/Madrid (YYYY-MM-DD). With granularity week or month it is the first day of the bucket (the Monday, or the 1st of the month). | [optional]
**value** | Option<**f64**> | Null when the metric has no value for the bucket, e.g. a rate, position or sentiment metric on a day without answers. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


