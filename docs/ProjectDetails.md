# ProjectDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**name** | Option<**String**> | Internal project label (sidebar, settings, admin) | [optional]
**brand_name** | Option<**String**> | LLM-facing brand label (used in prompts and customer-facing charts). Null when not set, in which case prompts and charts use `name`. | [optional]
**url** | Option<**String**> |  | [optional]
**description** | Option<**String**> |  | [optional]
**matching_names** | Option<**Vec<String>**> |  | [optional]
**industry** | Option<**serde_json::Value**> | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings when the project was created with a list or the in-app multi-select. Deliberately untyped so generated clients decode either shape | [optional]
**business_model** | Option<**String**> |  | [optional]
**business_model_other** | Option<**String**> | Set only when business_model is OTHER | [optional]
**primary_products** | Option<**Vec<String>**> |  | [optional]
**target_audience** | Option<**String**> |  | [optional]
**brand_voice** | Option<**String**> |  | [optional]
**goals** | Option<**String**> |  | [optional]
**country_code** | Option<**String**> |  | [optional]
**language_code** | Option<**String**> |  | [optional]
**paused** | Option<**bool**> |  | [optional]
**google_play_id** | Option<**String**> |  | [optional]
**app_store_id** | Option<**String**> |  | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**stats** | Option<[**models::ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md)> |  | [optional]
**data_coverage** | Option<[**models::ProjectDetailsAllOfDataCoverage**](ProjectDetailsAllOfDataCoverage.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


