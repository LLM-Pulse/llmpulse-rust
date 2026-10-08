# PromptRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**prompt_text** | **String** |  | 
**collection_id** | Option<**i32**> | Primary tag, when the prompt has one | 
**collection_ids** | **Vec<i32>** | Every tag the prompt belongs to | 
**tags** | [**Vec<models::TagRef>**](TagRef.md) |  | 
**country_code** | Option<**String**> |  | 
**language_code** | Option<**String**> |  | 
**prompt_type** | Option<**String**> | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified | 
**brand_kind** | Option<**String**> | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified | 
**last_executed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Null until the prompt has run | 
**app_url** | **String** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


