# CitationPageCache

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**present** | **bool** | Whether the page has a saved copy | 
**last_crawled_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the saved copy was read; null without usable content | 
**status_code** | Option<**i32**> | A saved successful response or an observed 404/410; null otherwise | 
**error_message** | Option<**String**> | Always null; crawl errors are not exposed | 
**content_format** | Option<**String**> |  | 
**bytes** | Option<**i32**> |  | 
**html_title** | Option<**String**> |  | 
**meta_title** | Option<**String**> |  | 
**meta_description** | Option<**String**> |  | 
**h1** | Option<**String**> |  | 
**canonical_url** | Option<**String**> |  | 
**language** | Option<**String**> |  | 
**mentions_processed** | **bool** | Whether the page's mention analysis has completed for this project | 
**content_available** | **bool** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


