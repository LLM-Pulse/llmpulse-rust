# TechnicalGeoReportsCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**url** | **String** | The URL analysed | 
**country_code** | **String** | The country used, the project country when none was sent | 
**output_language_code** | **String** | ISO 639-1 code the llms.txt files are written in, or auto for the website's own language | 
**batch_id** | Option<**i32**> | Bundle id, for the batch_id filter of GET /technical_geo_reports; null when no report was created | 
**created_reports** | **Vec<String>** | The report_type of every report created | 
**report_ids** | **std::collections::HashMap<String, i32>** | The id of each created report, by report_type | 
**app_urls** | **std::collections::HashMap<String, String>** | The link that opens each created report in the app, by report_type | 
**failed_reports** | [**Vec<models::TechnicalGeoReportsCreateResponseFailedReportsInner>**](TechnicalGeoReportsCreateResponseFailedReportsInner.md) | Reports that could not be created, with the reasons | 
**next_endpoint** | **String** | Path template to poll each created report | 
**poll_after_seconds** | **i32** | Seconds to wait before the first poll | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


