# CatalogPromptSuggestionsAcceptResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**accepted** | [**Vec<models::CatalogPromptSuggestionsAcceptResponseAcceptedInner>**](CatalogPromptSuggestionsAcceptResponseAcceptedInner.md) |  | 
**skipped** | [**Vec<models::CatalogPromptSuggestionsAcceptResponseSkippedInner>**](CatalogPromptSuggestionsAcceptResponseSkippedInner.md) |  | 
**prompts_available** | Option<**i32**> | Prompt slots left on the plan; null when unlimited | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


