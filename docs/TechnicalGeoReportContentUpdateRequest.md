# TechnicalGeoReportContentUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**report_type** | **ReportType** | Only llms_txt reports have editable content (enum: llms_txt) | 
**content_version** | **String** | result_data.content_version of the report as last read. It changes on every save; a value that no longer matches is refused as stale | 
**edits** | [**models::TechnicalGeoReportContentUpdateRequestEdits**](TechnicalGeoReportContentUpdateRequestEdits.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


