# Project

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**name** | Option<**String**> | Internal project label (sidebar, settings, admin) | [optional]
**brand_name** | Option<**String**> | LLM-facing brand label (used in prompts and customer-facing charts). Null when not set, in which case prompts and charts use `name`. | [optional]
**tracked** | Option<**bool**> | Whether scheduled runs include this project. False when it is paused, or when the plan's project limit leaves it out (the oldest projects up to the limit run), so its prompts do not run | [optional]
**untracked_reason** | Option<**String**> | Why tracked is false: paused or project_limit. Null when tracked | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


