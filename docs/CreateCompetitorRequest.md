# CreateCompetitorRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**brand_name** | **String** |  | 
**domain** | **String** | URL is accepted and normalised to host (e.g. https://www.openai.com → openai.com) | 
**matching_names** | Option<**Vec<String>**> | Extra names this competitor is matched by; brand_name is added automatically. At most 50 names in all, brand_name included, of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) | [optional]
**citation_match_mode** | Option<**CitationMatchMode**> | domain includes the registrable domain and all subdomains; host requires the exact hostname; path_prefix also requires citation_match_path (enum: domain, host, path_prefix) | [optional][default to Domain]
**citation_match_path** | Option<**String**> | Required when citation_match_mode=path_prefix, e.g. /es. Case-sensitive; trailing slash is optional; query and fragment are ignored | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


