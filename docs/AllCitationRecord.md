# AllCitationRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** | The citation's id, unique within its actor_type | 
**actor_type** | **String** | project (your brand) or competitor | 
**competitor_id** | Option<**i32**> | Competitor rows only | [optional]
**name** | Option<**String**> | The project's brand name (its name when no brand name is set), or the competitor's brand name | 
**domain** | Option<**String**> | On project rows the host of the cited URL without www. (null when it has no parsable host); on competitor rows the competitor's bare domain | 
**prompt_id** | **i32** |  | 
**prompt_execution_id** | **i32** |  | 
**url** | **String** | Normalized cited URL (tracking parameters and fragment removed) | 
**position** | Option<**i32**> | Rank of the citation in the answer; 0 for a background source reference with no visible rank | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


