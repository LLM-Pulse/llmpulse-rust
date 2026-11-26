# CompetitorCitationRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**competitor_id** | **i32** |  | 
**name** | **String** | The competitor's brand name | 
**domain** | **String** | The competitor's bare domain | 
**prompt_execution_id** | **i32** |  | 
**url** | **String** | Normalized cited URL (tracking parameters and fragment removed) | 
**position** | Option<**i32**> | Rank of the citation in the answer; 0 for a background source reference with no visible rank | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


