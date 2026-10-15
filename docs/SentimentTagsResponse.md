# SentimentTagsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**page** | **i32** |  | 
**per_page** | **i32** |  | 
**total** | **i32** | Rows matching the filters across every page | 
**request_id** | **String** |  | 
**from** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**to** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**brand** | [**models::SentimentBreakdownBrand**](SentimentBreakdownBrand.md) |  | 
**sort** | **String** |  | 
**sort_dir** | **String** |  | 
**data** | [**Vec<models::SentimentTagRow>**](SentimentTagRow.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


