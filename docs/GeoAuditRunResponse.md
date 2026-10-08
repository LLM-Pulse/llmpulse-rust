# GeoAuditRunResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**sequence** | Option<**i32**> | Run number within the audit, starting at 1 | [optional]
**status** | Option<**Status**> |  (enum: queued, running, completed, failed, unreachable) | [optional]
**trigger** | Option<**Trigger**> |  (enum: scheduled, manual, api, mcp, legacy_import) | [optional]
**score** | Option<**f64**> |  | [optional]
**grade** | Option<**String**> |  | [optional]
**score_delta** | Option<**f64**> | Score change against the previous completed run | [optional]
**comparable_to_previous** | Option<**bool**> | False when the checks or the audit settings changed since the previous run, so a diff may reflect that change | [optional]
**new_issues** | Option<**i32**> |  | [optional]
**fixed_issues** | Option<**i32**> |  | [optional]
**regressed_issues** | Option<**i32**> |  | [optional]
**error** | Option<**String**> |  | [optional]
**engine_version** | Option<**String**> |  | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**finished_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**app_url** | Option<**String**> |  | [optional]
**project_id** | Option<**i32**> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


