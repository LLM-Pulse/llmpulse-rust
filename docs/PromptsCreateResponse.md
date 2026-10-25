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
**untracked_reason** | Option<**String**> | Why tracked is false: paused or project_limit. Null when tracked | [optional]
**warning** | Option<**String**> | What to do when tracked is false. Null when tracked | [optional]
**data** | Option<[**Vec<models::PromptsCreateResponseDataInner>**](PromptsCreateResponseDataInner.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


