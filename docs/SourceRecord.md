# SourceRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**prompt_execution_id** | **i32** |  | 
**domain** | Option<**String**> | Registrable domain of the cited URL | 
**url** | Option<**String**> | Normalized cited URL (tracking parameters and fragment removed) | 
**url_sha256** | Option<**String**> | Key of the cited page, as GET /citation_intelligence/urls/{url_sha256} takes it | 
**position** | **i32** | Rank of the citation in the answer; 0 for a background source reference with no visible rank | 
**source_type** | **String** | owned (the project's domains), competitor or third_party | 
**is_google_play_link** | **bool** |  | 
**is_app_store_link** | **bool** |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


