# PeecExportImportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**import_id** | **i32** |  | 
**status** | **Status** | The import was accepted and finishes in the background (enum: started) | 
**prompts** | **i32** | Distinct prompts of the file, per country and language; each becomes a tracked prompt of the project | 
**new_prompts** | **i32** | The prompts the project does not hold yet, counted against the plan | 
**planned_answers** | **i32** | Weekly answers the import files (prompts x tracked AI models x weeks) | 
**models** | **std::collections::HashMap<String, String>** | Each AI model name of the file that is imported, with the tracked AI model its answers are filed under | 
**skipped_models** | **Vec<String>** | AI model names of the file whose answers are skipped, because the account does not track them | 
**detected_brands** | **Vec<String>** | Brand names the export's mentions column lists (up to 50), none of them created as competitors | 
**app_url** | **String** | Opens the project's prompts in the app | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


