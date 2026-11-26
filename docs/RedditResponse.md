# RedditResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**page** | **i32** |  | 
**per_page** | **i32** |  | 
**total** | **i32** | Rows matching the filters across every page | 
**request_id** | **String** |  | 
**view** | **String** | subreddits, authors, threads or breakdowns | 
**from** | **chrono::DateTime<chrono::FixedOffset>** | Start of the window, 30 days back by default | 
**to** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**citations** | Option<**i32**> | Reddit citations after the filters (view=breakdowns) | [optional]
**data** | [**Vec<models::RedditRow>**](RedditRow.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


