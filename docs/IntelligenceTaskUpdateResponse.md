# IntelligenceTaskUpdateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**public_id** | Option<**String**> |  | [optional]
**project_id** | Option<**i32**> |  | [optional]
**task_type** | Option<**String**> |  | [optional]
**title** | Option<**String**> |  | [optional]
**status** | Option<**String**> |  | [optional]
**prompt_id** | Option<**i32**> |  | [optional]
**prompt_text** | Option<**String**> |  | [optional]
**agentic_mode** | Option<**bool**> |  | [optional]
**custom_topic** | Option<**String**> |  | [optional]
**user_instructions** | Option<**String**> |  | [optional]
**output_language_code** | Option<**String**> |  | [optional]
**word_count** | Option<**i32**> |  | [optional]
**result_data** | Option<**serde_json::Value**> | Only present when status='completed' | [optional]
**error_message** | Option<**String**> |  | [optional]
**estimated_time** | Option<**String**> |  | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**processed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**manually_edited_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the content was last edited by hand; null while the output is as generated | [optional]
**edited_by_user_id** | Option<**i32**> | User behind the last manual edit; null for an unedited task or an edit made from an embedded portal | [optional]
**request_id** | Option<**String**> |  | [optional]
**changed_paths** | Option<**Vec<String>**> | Paths whose text actually changed; empty when every value matched the stored text | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


