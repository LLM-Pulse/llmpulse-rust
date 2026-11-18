# UrlListEntry

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**value** | **String** | The exact URL, \"host/path\" of a prefix, or the host of a domain rule. | 
**match_type** | **MatchType** |  (enum: url, prefix, domain) | 
**host** | **String** |  | 
**status** | **Status** |  (enum: cited, lost, not_cited) | 
**added_on** | **chrono::NaiveDate** |  | 
**cost** | Option<**f64**> |  | 
**channel** | Option<**String**> |  | 
**citations** | **i32** |  | 
**cited_pages** | **i32** |  | 
**first_cited_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**last_cited_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**days_to_first_citation** | Option<**i32**> |  | 
**avg_citation_position** | Option<**f64**> |  | 
**models** | **Vec<String>** |  | 
**brand_mentioned** | Option<**bool**> |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


