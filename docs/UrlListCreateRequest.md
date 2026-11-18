# UrlListCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**name** | **String** |  | 
**description** | Option<**String**> |  | [optional]
**currency** | Option<**Currency**> |  (enum: USD, EUR, GBP) | [optional][default to Usd]
**entries** | Option<[**Vec<models::UrlListEntryInput>**](UrlListEntryInput.md)> |  | [optional]
**match_type** | Option<**MatchType**> | Read every entry without its own match_type as this type. Default detects it from each value. (enum: url, prefix, domain) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


