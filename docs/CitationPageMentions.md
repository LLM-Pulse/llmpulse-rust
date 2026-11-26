# CitationPageMentions

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**brand_mentioned** | Option<**bool**> |  | 
**competitor_mentioned** | Option<**bool**> |  | 
**brand_position** | Option<**i32**> | Rank of the brand's first mention on the page; null when it has none | 
**content_gap_status** | **String** | missing_page_cache, content_unavailable, mentions_not_processed, mentioned, gap (a competitor but not the brand) or not_mentioned | 
**brands** | [**Vec<models::CitationPageMentionsBrandsInner>**](CitationPageMentionsBrandsInner.md) | Each brand the page mentions once, in order of first mention | 
**mentions** | Option<[**Vec<models::CitationPageMentionsMentionsInner>**](CitationPageMentionsMentionsInner.md)> | Every mention on the page with its snippet; not sent on GET /citation_intelligence/groups | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


