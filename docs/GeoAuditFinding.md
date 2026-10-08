# GeoAuditFinding

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**check_key** | Option<**String**> | Stable key of the check within its audit type | [optional]
**check_title** | Option<**String**> |  | [optional]
**subject_key** | Option<**String**> | What the check is about (site for site-wide checks, a bot slug for robots.txt bot checks) | [optional]
**subject** | Option<**String**> |  | [optional]
**status** | Option<**Status**> |  (enum: pass, warn, fail, info, not_applicable, unknown) | [optional]
**severity** | Option<**Severity**> |  (enum: critical, high, medium, low, info) | [optional]
**evidence** | Option<**serde_json::Value**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


