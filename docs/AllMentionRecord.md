# AllMentionRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** | The mention's id, unique within its actor_type | 
**actor_type** | **String** | project (your brand) or competitor | 
**competitor_id** | Option<**i32**> | Competitor rows only | [optional]
**name** | Option<**String**> | The project's brand name (its name when no brand name is set), or the competitor's brand name | 
**domain** | Option<**String**> | The competitor's bare domain (competitor rows only) | [optional]
**prompt_id** | **i32** |  | 
**prompt_execution_id** | **i32** |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


