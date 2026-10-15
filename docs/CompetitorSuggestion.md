# CompetitorSuggestion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **String** | The suggestion key (brands) or the id of one citing source row (citations) | 
**domain** | **String** |  | 
**brand_name** | Option<**String**> | The proposed brand name; null for a cited domain | [optional]
**matching_names** | **Vec<String>** | The names a tracked competitor would be matched by; empty for a cited domain | 
**mentions** | Option<**i32**> | Answers naming the brand, when the discovery counted them (brands only) | [optional]
**citations** | Option<**i32**> | Answers citing the domain (citations only) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


