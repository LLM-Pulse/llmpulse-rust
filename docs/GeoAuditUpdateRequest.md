# GeoAuditUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**cadence** | Option<**Cadence**> |  (enum: once, weekly, monthly) | [optional]
**schedule_day** | Option<**i32**> | Weekly: 0 (Sunday) to 6. Monthly: 1 to 28. | [optional]
**schedule_hour** | Option<**i32**> | Hour of the day, 0 to 23, in the audit time zone | [optional]
**status** | Option<**Status**> | paused stops scheduled runs, active resumes them, archived is the same as DELETE (enum: active, paused, archived) | [optional]
**email_alerts** | Option<**bool**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


