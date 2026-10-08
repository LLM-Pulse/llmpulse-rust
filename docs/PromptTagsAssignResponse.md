# PromptTagsAssignResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**prompts_targeted** | **i32** | Prompts of the project among prompt_ids | 
**tags_attached** | [**Vec<models::TagRef>**](TagRef.md) |  | 
**new_links_created** | **i32** |  | 
**skipped_already_linked** | **i32** |  | 
**missing_tag_names** | **Vec<String>** | tag_names that matched no tag and were not created | 
**ignored_prompt_ids** | **Vec<i32>** | prompt_ids that are not prompts of this project | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


