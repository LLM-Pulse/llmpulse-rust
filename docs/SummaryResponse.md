# SummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**granularity** | Option<**String**> |  | [optional]
**filters** | Option<**serde_json::Value**> |  | [optional]
**series** | Option<[**std::collections::HashMap<String, Vec<models::TimeseriesSeries>>**](Vec.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]
**summary** | Option<[**std::collections::HashMap<String, Vec<models::SummaryResponseAllOfSummaryValueInner>>**](Vec.md)> |  | [optional]
**position_distribution** | Option<[**models::SummaryResponseAllOfPositionDistribution**](SummaryResponseAllOfPositionDistribution.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


