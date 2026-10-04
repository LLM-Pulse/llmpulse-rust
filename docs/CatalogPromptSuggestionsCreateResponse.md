# CatalogPromptSuggestionsCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**created** | **i32** |  | 
**skipped** | **i32** | Generated prompts not saved because the project already holds them as a suggestion (from any source or product, in any status). | 
**data** | [**Vec<models::CatalogPromptSuggestion>**](CatalogPromptSuggestion.md) |  | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


