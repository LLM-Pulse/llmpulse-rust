# ProjectProfile

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**name** | **String** |  | 
**brand_name** | Option<**String**> |  | [optional]
**description** | Option<**String**> |  | [optional]
**industry** | Option<**serde_json::Value**> | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings. Deliberately untyped so generated clients decode either shape | [optional]
**business_model** | Option<**String**> |  | [optional]
**business_model_other** | Option<**String**> | Set only when business_model is OTHER | [optional]
**target_audience** | Option<**String**> |  | [optional]
**primary_products** | Option<**Vec<String>**> |  | [optional]
**brand_voice** | Option<**String**> |  | [optional]
**goals** | Option<**String**> |  | [optional]
**matching_names** | **Vec<String>** |  | 
**additional_owned_domains** | **Vec<String>** | Other domains the brand owns (at most 10, each a website's own domain covering its subdomains), whose citations count as owned like the project website. Empty when none | 
**prompt_limit** | Option<**i32**> | The most prompts this project can hold, set by the account owner or a co-owner (Account Settings > Prompt Limits). Null when the project has no limit of its own; the account's plan allowance applies either way | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


