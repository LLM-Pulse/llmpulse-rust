# CitationRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**name** | **String** | The project's brand name (its name when no brand name is set) | 
**domain** | Option<**String**> | Host of the cited URL without www.; null when the URL has no parsable host | 
**prompt_id** | **i32** |  | 
**prompt_execution_id** | **i32** |  | 
**url** | **String** | Normalized cited URL (tracking parameters and fragment removed) | 
**position** | Option<**i32**> | Rank of the citation in the answer; 0 for a background source reference with no visible rank | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


