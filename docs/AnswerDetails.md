# AnswerDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**prompt_id** | Option<**i32**> |  | [optional]
**prompt_text** | Option<**String**> |  | [optional]
**model** | Option<**String**> |  | [optional]
**response** | Option<**String**> |  | [optional]
**response_truncated** | Option<**bool**> |  | [optional]
**executed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**duration_ms** | Option<**f64**> | Milliseconds, rounded to one decimal place | [optional]
**success** | Option<**bool**> | Null while the answer is still pending | [optional]
**no_result** | Option<**bool**> | True for a sentinel non-answer (the provider returned nothing after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics | [optional]
**fan_out_queries** | Option<**Vec<String>**> |  | [optional]
**mentions** | Option<**Vec<serde_json::Value>**> |  | [optional]
**citations** | Option<**Vec<serde_json::Value>**> |  | [optional]
**competitor_mentions** | Option<**Vec<serde_json::Value>**> |  | [optional]
**competitor_citations** | Option<**Vec<serde_json::Value>**> |  | [optional]
**sentiments** | Option<**Vec<serde_json::Value>**> | Needs the Growth plan or above; left out below it and named in plan_required_fields | [optional]
**sources** | Option<**Vec<serde_json::Value>**> |  | [optional]
**shopping_products** | Option<**Vec<serde_json::Value>**> | Needs the Scale plan or above; left out below it and named in plan_required_fields | [optional]
**brand_entities** | Option<**Vec<serde_json::Value>**> |  | [optional]
**local_businesses** | Option<**Vec<serde_json::Value>**> |  | [optional]
**locale** | Option<[**models::AnswerDetailsLocale**](AnswerDetailsLocale.md)> |  | [optional]
**plan_required_fields** | **Vec<String>** | The fields left out of this answer because the account's plan does not include them (sentiments below Growth, shopping_products below Scale). Always present, empty when nothing is left out | 
**app_url** | Option<**String**> | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


