# CitationGroupRowAggregateDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**unique_urls_count** | **i32** |  | 
**crawled_urls_count** | **i32** | Pages with usable content | 
**brand_mentioned_urls_count** | Option<**i32**> | Pages analyzed for the project that mention the brand; null when none is analyzed | 
**competitor_mentioned_urls_count** | Option<**i32**> | Pages analyzed for the project that mention a competitor; null when none is analyzed | 
**last_crawled_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


