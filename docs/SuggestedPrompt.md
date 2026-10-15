# SuggestedPrompt

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**prompt** | **String** |  | 
**source** | **String** | The generator that wrote it: website, magic (keyword runs), topic, reddit, paa, reputational, translate, gsc (Search Console) or catalog | 
**status** | **String** | pending, accepted or rejected | 
**country_code** | Option<**String**> |  | 
**language_code** | Option<**String**> |  | 
**prompt_id** | Option<**i32**> | The prompt an accepted suggestion became | 
**accepted_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


