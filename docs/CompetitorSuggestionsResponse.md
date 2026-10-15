# CompetitorSuggestionsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**page** | **i32** |  | 
**per_page** | **i32** |  | 
**total** | **i32** | Rows matching the filters across every page | 
**request_id** | **String** |  | 
**basis** | **Basis** |  (enum: brands, citations) | 
**discovery** | [**models::CompetitorDiscoveryState**](CompetitorDiscoveryState.md) |  | 
**data** | [**Vec<models::CompetitorSuggestion>**](CompetitorSuggestion.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


