# PromptSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**filters** | Option<**serde_json::Value**> |  | [optional]
**breakdown** | Option<**String**> |  | [optional]
**sort** | Option<**String**> |  | [optional]
**sort_dir** | Option<**String**> |  | [optional]
**page** | Option<**i32**> |  | [optional]
**per_page** | Option<**i32**> |  | [optional]
**total** | Option<**i32**> |  | [optional]
**data** | Option<[**Vec<models::PromptSummaryRow>**](PromptSummaryRow.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


