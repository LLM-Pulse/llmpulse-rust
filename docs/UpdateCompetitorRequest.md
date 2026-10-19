# UpdateCompetitorRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**brand_name** | Option<**String**> |  | [optional]
**domain** | Option<**String**> | Website domain or host used for citation matching. A full URL is accepted and normalised to its host. | [optional]
**matching_names** | Option<**Vec<String>**> | FULL replacement list of the names this competitor is matched by; brand_name is added automatically. At most 50 names in all, brand_name included, of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) and nothing in the request is applied | [optional]
**color** | Option<**String**> | Hex color, e.g. #1a2b3c | [optional]
**citation_match_mode** | Option<**CitationMatchMode**> |  (enum: domain, host, path_prefix) | [optional]
**citation_match_path** | Option<**String**> | Required when changing citation_match_mode to path_prefix | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


