# SuggestedPromptsAcceptRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**ids** | **Vec<i32>** | Suggestion ids to accept (max 100) | 
**tag_ids** | Option<**Vec<i32>**> | One tag id to put the new prompts in | [optional]
**tag_names** | Option<**Vec<String>**> | One tag name (case-insensitive) to put the new prompts in | [optional]
**create_missing** | Option<**bool**> | Create the tag named in tag_names when it does not exist | [optional][default to false]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


