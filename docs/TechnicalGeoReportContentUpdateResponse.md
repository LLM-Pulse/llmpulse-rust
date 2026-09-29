# TechnicalGeoReportContentUpdateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**report_type** | Option<**String**> | Always llms_txt | [optional]
**project_id** | Option<**i32**> |  | [optional]
**batch_id** | Option<**i32**> | Bundle the report was created in; null for a report created on its own | [optional]
**url** | Option<**String**> | Always null for llms_txt reports; domain names the website | [optional]
**domain** | Option<**String**> |  | [optional]
**country_code** | Option<**String**> |  | [optional]
**output_language_code** | Option<**String**> | ISO 639-1 code the files were requested in; null when they are written in the website's own language | [optional]
**status** | Option<**String**> |  | [optional]
**result_available** | Option<**bool**> |  | [optional]
**overall_score** | Option<**f64**> | Always null for llms_txt reports | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**updated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**result_data** | Option<[**models::LlmsTxtTechnicalGeoReportResultData**](LlmsTxtTechnicalGeoReportResultData.md)> |  | [optional]
**error_message** | Option<**String**> |  | [optional]
**poll_after_seconds** | Option<**i32**> | Seconds to wait before polling again while the report runs; null once it has finished | [optional]
**app_url** | Option<**String**> | Opens this report in the app | [optional]
**request_id** | Option<**String**> |  | [optional]
**changed_files** | Option<**Vec<ChangedFiles>**> | Files whose text actually changed; empty when every file matched the stored text (enum: llms_txt, llms_full_txt) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


