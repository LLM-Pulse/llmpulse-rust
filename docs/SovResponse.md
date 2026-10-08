# SovResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**granularity** | Option<**String**> | day, week or month | [optional]
**filters** | Option<[**models::MetricsFiltersEcho**](MetricsFiltersEcho.md)> |  | [optional]
**periods** | Option<[**Vec<models::SovResponsePeriodsInner>**](SovResponsePeriodsInner.md)> | Per-bucket sample size and completeness: mentions is the total the shares were computed on (1-3 mentions produce the 100/50/33.33 low-sample patterns); partial marks buckets still collecting data or clipped by the requested window; confidence and margin_of_error read the sample size. | [optional]
**sample** | Option<[**models::SovResponseSample**](SovResponseSample.md)> |  | [optional]
**over_time** | Option<[**Vec<models::SovResponseOverTimeInner>**](SovResponseOverTimeInner.md)> |  | [optional]
**current** | Option<[**Vec<models::SovResponseCurrentInner>**](SovResponseCurrentInner.md)> |  | [optional]
**breakdown** | Option<[**Vec<models::SovResponseBreakdownInner>**](SovResponseBreakdownInner.md)> |  | [optional]
**others** | Option<[**Vec<models::SovResponseOthersInner>**](SovResponseOthersInner.md)> | Actors ranked fifth and below, folded into the Others share of breakdown | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


