# AiOrdersUpdateRequestDaysInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**day** | **chrono::NaiveDate** | Must fall inside from..to | 
**referrer** | **String** | Raw referring host or utm_source of the order's first visit, e.g. chatgpt.com. Entries that are not an AI assistant are ignored | 
**orders** | **u32** |  | 
**revenue** | **String** | Non-negative decimal amount in currency, e.g. 120.50. A JSON number is accepted too | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


