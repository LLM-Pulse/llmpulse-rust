# CompetitorUpdateResponseCompetitor

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**brand_name** | **String** |  | 
**domain** | **String** |  | 
**citation_match_mode** | [**models::CitationMatchMode**](CitationMatchMode.md) |  | 
**citation_match_path** | Option<**String**> | Set only when citation_match_mode is path_prefix | 
**color** | Option<**String**> |  | 
**matching_names** | **Vec<String>** |  | 
**processing** | **bool** | True while historical mention and citation matching is recalculated in the background | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


