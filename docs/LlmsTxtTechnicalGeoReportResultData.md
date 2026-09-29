# LlmsTxtTechnicalGeoReportResultData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**llms_txt_content** | Option<**String**> | Current llms.txt, manual edits included | [optional]
**llms_full_txt_content** | Option<**String**> | Current llms-full.txt, manual edits included | [optional]
**manually_edited_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the files were last edited by hand in the app, the API or MCP; null while they are as generated | [optional]
**content_version** | Option<**String**> | Send it back as content_version when editing the files. It changes on every save | [optional]
**original_llms_txt_content** | Option<**String**> | The generated llms.txt, kept from the first manual edit; null while the files are as generated | [optional]
**original_llms_full_txt_content** | Option<**String**> | The generated llms-full.txt, kept from the first manual edit; null while the files are as generated | [optional]
**crawl_data** | Option<**serde_json::Value**> |  | [optional]
**metadata** | Option<**serde_json::Value**> | Generation details, including output_language_code, the language the files were written in | [optional]
**pages_crawled** | Option<**i32**> |  | [optional]
**generation_time_ms** | Option<**i32**> |  | [optional]
**openai_tokens_used** | Option<**i32**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


