# CitingDomainMentionShareResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**filters** | [**models::CitationIntelligenceFiltersEcho**](CitationIntelligenceFiltersEcho.md) |  | 
**normalization** | **String** | How the shares are computed | 
**data** | [**Vec<models::CitingDomainMentionShareResponseDataInner>**](CitingDomainMentionShareResponseDataInner.md) | One row per requested domain (normalized, at most 50), in the order given | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


