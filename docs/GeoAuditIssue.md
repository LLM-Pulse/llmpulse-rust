# GeoAuditIssue

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**check_key** | Option<**String**> |  | [optional]
**check_title** | Option<**String**> |  | [optional]
**subject_key** | Option<**String**> |  | [optional]
**subject** | Option<**String**> |  | [optional]
**severity** | Option<**String**> |  | [optional]
**state** | Option<**State**> |  (enum: open, fixed, gone) | [optional]
**badge** | Option<**Badge**> | How the latest comparable run moved the issue (enum: new, persisting, regressed, fixed, gone) | [optional]
**accepted** | Option<**bool**> |  | [optional]
**accepted_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**regression_count** | Option<**i32**> |  | [optional]
**evidence** | Option<**serde_json::Value**> |  | [optional]
**updated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


