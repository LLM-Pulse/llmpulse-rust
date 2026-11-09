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
**tracked** | **bool** | Whether scheduled runs include the project the prompts were imported into. False when it is paused or beyond the plan's project limit, so the new prompts do not run until that changes | 
**untracked_reason** | Option<**String**> | Why tracked is false: pitch_project, paused or project_limit. Null when tracked | 
**warning** | Option<**String**> | What to do when tracked is false, or why some first runs wait when first_runs_wait_until is set. Null otherwise | 
**first_runs_wait_until** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Set when the account's allowance of AI answers left this cycle, or the project's own share of it when the account caps each project's executions, cannot give every new prompt one answer per enabled AI model, so the rest run when the allowance resets at this time (00:00 Europe/Madrid). It counts this request's prompts against what was left when it arrived, not first runs other requests queued moments earlier. Null otherwise, when the allowance is unlimited, when tracked is false or when the account is not active | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


