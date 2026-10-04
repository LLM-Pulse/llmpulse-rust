# CatalogPromptSuggestion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**prompt** | **String** |  | 
**status** | **String** | pending, accepted or rejected | 
**source** | **String** | Always catalog | 
**country_code** | Option<**String**> |  | 
**language_code** | Option<**String**> |  | 
**product** | [**models::CatalogPromptSuggestionProduct**](CatalogPromptSuggestionProduct.md) |  | 
**prompt_id** | Option<**i32**> | The tracked prompt an accepted suggestion became; null until accepted | 
**accepted_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the suggestion was accepted; null until then | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


