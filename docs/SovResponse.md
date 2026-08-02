# SovResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**periods** | Option<[**Vec<models::SovResponsePeriodsInner>**](SovResponsePeriodsInner.md)> | Per-bucket sample size and completeness: mentions is the total the shares were computed on (1-3 mentions produce the 100/50/33.33 low-sample patterns); partial marks buckets still collecting data or clipped by the requested window. | [optional]
**over_time** | Option<[**Vec<models::SovResponseOverTimeInner>**](SovResponseOverTimeInner.md)> |  | [optional]
**current** | Option<[**Vec<models::SovResponseCurrentInner>**](SovResponseCurrentInner.md)> |  | [optional]
**breakdown** | Option<[**Vec<models::SovResponseBreakdownInner>**](SovResponseBreakdownInner.md)> |  | [optional]
**others** | Option<**Vec<serde_json::Value>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


