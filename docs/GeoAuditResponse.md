# GeoAuditResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**String**> | Stable audit id | [optional]
**audit_type** | Option<**AuditType**> |  (enum: agent_readiness, robots_txt, crawlability, schema, content_readiness, discoverability, site_structure) | [optional]
**target** | Option<**String**> | The audited domain (site-wide types) or page URL, normalized | [optional]
**country_code** | Option<**String**> |  | [optional]
**cadence** | Option<**Cadence**> |  (enum: once, weekly, monthly) | [optional]
**status** | Option<**Status**> |  (enum: active, paused, archived) | [optional]
**paused_reason** | Option<**String**> | user, or unreachable when three runs in a row could not reach the site | [optional]
**schedule** | Option<[**models::GeoAuditSchedule**](GeoAuditSchedule.md)> |  | [optional]
**next_run_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**email_alerts** | Option<**bool**> |  | [optional]
**recurring_available** | Option<**bool**> | Whether this audit type can run weekly or monthly | [optional]
**checks_tracked** | Option<**bool**> | Whether runs of this type produce findings and issues, or a score only | [optional]
**latest_run** | Option<[**models::GeoAuditRun**](GeoAuditRun.md)> |  | [optional]
**open_issues** | Option<**i32**> |  | [optional]
**open_critical_issues** | Option<**i32**> |  | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**app_url** | Option<**String**> |  | [optional]
**project_id** | Option<**i32**> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


