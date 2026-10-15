# PromptGenerationResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** | The run id; poll GET /prompt_generations/{id} with it (kept for 24 hours) | 
**project_id** | **i32** |  | 
**source** | **String** |  | 
**status** | **Status** |  (enum: processing, completed, failed) | 
**params** | [**models::PromptGenerationResponseParams**](PromptGenerationResponseParams.md) |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**finished_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**suggestions_count** | **i32** |  | 
**suggestions** | [**Vec<models::SuggestedPrompt>**](SuggestedPrompt.md) | The suggestions the run saved to the Suggested prompts queue, with their current status | 
**error** | Option<[**models::PromptGenerationResponseError**](PromptGenerationResponseError.md)> |  | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


