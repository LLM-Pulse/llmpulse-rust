# PromptsImportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**processed_rows** | **i32** | Distinct rows imported or matched to an existing prompt | 
**created** | **i32** |  | 
**duplicates** | **i32** | Rows that matched an existing prompt (they still get the row's tags, unless a team member lacks update access to Prompts) | 
**tagged** | **i32** | New prompt-tag links | 
**created_tags** | **i32** |  | 
**row_errors** | [**Vec<models::PromptsImportResponseRowErrorsInner>**](PromptsImportResponseRowErrorsInner.md) | Rows that were skipped or whose tags were not added, by their index in rows | 
**length_warning** | Option<**String**> | Which tracked AI models will skip new prompts that are too long for them | 
**prompts_available** | Option<**i32**> | Prompt slots left on the plan; null when unlimited | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


