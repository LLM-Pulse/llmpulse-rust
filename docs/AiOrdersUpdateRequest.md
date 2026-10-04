# AiOrdersUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**platform** | **Platform** |  (enum: shopify) | 
**currency** | **String** | ISO 4217 code, e.g. EUR | 
**from** | **chrono::NaiveDate** | First day of the window this push replaces | 
**to** | **chrono::NaiveDate** | Last day of the window; at most 400 days after from | 
**days** | [**Vec<models::AiOrdersUpdateRequestDaysInner>**](AiOrdersUpdateRequestDaysInner.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


