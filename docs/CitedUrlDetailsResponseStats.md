# CitedUrlDetailsResponseStats

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total_responses** | **i32** | Answers citing the URL under the filters | 
**total_citations** | **i32** |  | 
**citation_rate** | **f64** | total_responses as a percentage (0-100) of citation_rate_denominator | 
**citation_rate_denominator** | **i32** | Answers matching the filters | 
**avg_citation_position** | Option<**f64**> | Null when no visible citation has a rank | 
**first_seen_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Null when no citation matches the filters | 
**last_seen_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Null when no citation matches the filters | 
**distinct_urls** | **i32** | Spellings of the URL cited (tracking parameters, a trailing slash) | 
**source_types** | [**models::CitedUrlDetailsResponseStatsSourceTypes**](CitedUrlDetailsResponseStatsSourceTypes.md) |  | 
**models** | **std::collections::HashMap<String, i32>** | Answers citing the URL per AI model, keyed by model | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


