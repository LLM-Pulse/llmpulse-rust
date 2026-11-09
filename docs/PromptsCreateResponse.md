# PromptsCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**created** | Option<**i32**> |  | [optional]
**skipped** | Option<**i32**> |  | [optional]
**total_after** | Option<**i32**> |  | [optional]
**prompts_available** | Option<**i32**> |  | [optional]
**tracked** | Option<**bool**> | Whether scheduled runs include the project the prompts were added to. False when it is paused or beyond the plan's project limit, so the new prompts do not run until that changes | [optional]
**untracked_reason** | Option<**String**> | Why tracked is false: pitch_project, paused or project_limit. Null when tracked | [optional]
**warning** | Option<**String**> | What to do when tracked is false, or why some first runs wait when first_runs_wait_until is set. Null otherwise | [optional]
**first_runs_wait_until** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Set when the account's allowance of AI answers left this cycle, or the project's own share of it when the account caps each project's executions, cannot give every new prompt one answer per enabled AI model, so the rest run when the allowance resets at this time (00:00 Europe/Madrid). It counts this request's prompts against what was left when it arrived, not first runs other requests queued moments earlier. Null otherwise, when the allowance is unlimited, when tracked is false or when the account is not active | [optional]
**data** | Option<[**Vec<models::PromptsCreateResponseDataInner>**](PromptsCreateResponseDataInner.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


