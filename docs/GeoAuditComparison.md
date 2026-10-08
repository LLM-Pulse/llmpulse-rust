# GeoAuditComparison

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**from_run** | Option<[**models::GeoAuditRun**](GeoAuditRun.md)> |  | [optional]
**to_run** | Option<[**models::GeoAuditRun**](GeoAuditRun.md)> |  | [optional]
**comparable** | Option<**bool**> |  | [optional]
**score_delta** | Option<**f64**> |  | [optional]
**metric_deltas** | Option<**std::collections::HashMap<String, f64>**> |  | [optional]
**counts** | Option<**std::collections::HashMap<String, i32>**> |  | [optional]
**changes** | Option<[**Vec<models::GeoAuditComparisonChangesInner>**](GeoAuditComparisonChangesInner.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


