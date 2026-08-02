# AgentTrafficResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**from** | Option<**chrono::NaiveDate**> |  | [optional]
**to** | Option<**chrono::NaiveDate**> |  | [optional]
**group_by** | Option<**GroupBy**> |  (enum: bot, company) | [optional]
**granularity** | Option<**Granularity**> |  (enum: day, week, month) | [optional]
**totals** | Option<**std::collections::HashMap<String, i32>**> |  | [optional]
**timeseries** | Option<**std::collections::HashMap<String, std::collections::HashMap<String, i32>>**> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


