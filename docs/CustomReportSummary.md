# CustomReportSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**name** | **String** |  | 
**date_range** | [**models::CustomReportDateRange**](CustomReportDateRange.md) |  | 
**schedule** | [**models::CustomReportSchedule**](CustomReportSchedule.md) |  | 
**recipients_count** | **i32** |  | 
**published** | **bool** | Whether the shared link is published | 
**public_link_active** | **bool** | Whether the shared link opens (published and not made inside a client portal) | 
**password_protected** | **bool** |  | 
**portal_only** | **bool** | Made inside a client portal, so it cannot be shared or emailed | 
**widget_count** | **i32** |  | 
**widgets** | [**Vec<models::CustomReportWidgetRef>**](CustomReportWidgetRef.md) |  | 
**last_sent_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the report was last emailed, on its schedule or with Send now | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


