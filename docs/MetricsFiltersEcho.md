# MetricsFiltersEcho

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**metrics** | Option<**Vec<String>**> | Requested metrics after alias resolution (mention_rate is echoed as visibility) | [optional]
**granularity** | Option<**String**> | day, week or month | [optional]
**model** | Option<**String**> | The model filter, or null when absent or not enabled for the account | [optional]
**collection_id** | Option<**String**> | The collection_id parameter as sent (one id or a comma-separated list) | [optional]
**collection_ids** | Option<**Vec<i32>**> |  | [optional]
**domains** | Option<**Vec<String>**> |  | [optional]
**country_code** | Option<**String**> | Comma-separated country codes | [optional]
**language_code** | Option<**String**> | Comma-separated language codes | [optional]
**prompt** | Option<**i32**> | The prompt id filter | [optional]
**prompt_type** | Option<**String**> | Comma-separated prompt types | [optional]
**brand_kind** | Option<**String**> |  | [optional]
**competitors** | Option<**Vec<i32>**> | Competitor ids from the competitors parameter; empty when it was not given | [optional]
**include_project** | Option<**bool**> |  | [optional]
**query** | Option<**String**> | Only present when a query filter was given | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


