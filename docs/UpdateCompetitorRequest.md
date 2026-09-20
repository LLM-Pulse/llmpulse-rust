# UpdateCompetitorRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**brand_name** | Option<**String**> |  | [optional]
**domain** | Option<**String**> | Website domain or host used for citation matching. A full URL is accepted and normalised to its host. | [optional]
**matching_names** | Option<**Vec<String>**> |  | [optional]
**color** | Option<**String**> | Hex color, e.g. #1a2b3c | [optional]
**citation_match_mode** | Option<**CitationMatchMode**> |  (enum: domain, host, path_prefix) | [optional]
**citation_match_path** | Option<**String**> | Required when changing citation_match_mode to path_prefix | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


