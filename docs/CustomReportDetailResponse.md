# CustomReportDetailResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**id** | **i32** |  | 
**name** | **String** |  | 
**date_range** | [**models::CustomReportDateRange**](CustomReportDateRange.md) |  | 
**schedule** | [**models::CustomReportSchedule**](CustomReportSchedule.md) |  | 
**recipients_count** | Option<**i32**> |  | [optional]
**published** | Option<**bool**> |  | [optional]
**public_link_active** | Option<**bool**> |  | [optional]
**password_protected** | Option<**bool**> |  | [optional]
**portal_only** | Option<**bool**> |  | [optional]
**last_sent_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the report was last emailed, on its schedule or with Send now | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**updated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**filters** | [**models::CustomReportFilters**](CustomReportFilters.md) |  | 
**compare_previous** | Option<**bool**> |  | [optional]
**attach_excel** | Option<**bool**> |  | [optional]
**manual_send_available_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the 10-minute cooldown after the last manual send ends; null when none is running | [optional]
**generated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**blocks** | [**Vec<models::CustomReportBlock>**](CustomReportBlock.md) | The report layout in order | 
**widgets** | [**Vec<models::CustomReportWidget>**](CustomReportWidget.md) |  | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


