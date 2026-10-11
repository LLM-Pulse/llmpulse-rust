# IntelligenceTaskSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**public_id** | **String** |  | 
**task_type** | **String** |  | 
**title** | **String** |  | 
**status** | **String** |  | 
**prompt_id** | Option<**i32**> |  | 
**prompt_text** | Option<**String**> |  | 
**word_count** | Option<**i32**> |  | 
**manually_edited_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the content was last edited by hand; null while the output is as generated | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**processed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**result_version** | **String** | Concurrency token for content edits: send it back as result_version on PATCH /intelligence_tasks/{id} so an edit composed before a regeneration is refused with ERR_STALE_CONTENT (409). It is \"0\" until the task first completes, then changes each time a generation or regeneration replaces result_data, never on a manual edit or a revert. Treat it as opaque text | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


