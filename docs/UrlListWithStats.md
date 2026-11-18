# UrlListWithStats

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**name** | **String** |  | 
**description** | Option<**String**> |  | 
**currency** | **Currency** | The currency of the entry costs. (enum: USD, EUR, GBP) | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**entries_count** | **i32** |  | 
**cited_entries** | **i32** | Entries an AI answer cited in the window. | 
**citations** | **i32** | AI answers citing any entry in the window, each once. | 
**last_cited_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | The latest answer citing an entry, up to the window's end. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


