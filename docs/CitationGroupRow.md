# CitationGroupRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source_id** | **i32** | The group's first citation | 
**view** | **String** | url, domain or host | 
**key** | **String** | The URL as cited, the domain or the host | 
**total_responses** | **i32** | Answers citing it | 
**total_citations** | **i32** |  | 
**citation_rate** | **f64** | total_responses as a percentage (0-100) of citation_rate_denominator | 
**citation_rate_denominator** | **i32** | Answers matching the filters | 
**avg_citation_position** | Option<**f64**> | Null when no visible citation has a rank | 
**first_seen_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**last_seen_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**models** | **std::collections::HashMap<String, i32>** | Answers citing it per AI model, keyed by model | 
**url** | Option<**String**> | url view only. The URL as cited | [optional]
**url_sha256** | Option<**String**> | url view only. Key of the cited page, shared by the URL's variants | [optional]
**normalized_url** | Option<**String**> | url view only | [optional]
**page_cache** | Option<[**models::CitationPageCache**](CitationPageCache.md)> |  | [optional]
**page_mentions** | Option<[**models::CitationPageMentions**](CitationPageMentions.md)> |  | [optional]
**domain** | Option<**String**> | domain view only | [optional]
**host** | Option<**String**> | host view only | [optional]
**aggregate_details** | Option<[**models::CitationGroupRowAggregateDetails**](CitationGroupRowAggregateDetails.md)> |  | [optional]
**citation_series** | Option<[**models::CitationSeries**](CitationSeries.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


