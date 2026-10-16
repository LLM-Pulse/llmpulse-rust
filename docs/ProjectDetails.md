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
**additional_owned_domains** | Option<**Vec<String>**> | Other domains the brand owns (at most 10, each a website's own domain covering its subdomains), whose citations count as owned like the project website. Empty when none | [optional]
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
**prompt_limit** | Option<**i32**> | Maximum number of active prompts this project may hold, set by the account owner or a co-owner in Account Settings > Prompt Limits; null when the project has no limit of its own and only the account quota applies | [optional]
**stats** | Option<[**models::ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md)> |  | [optional]
**data_coverage** | Option<[**models::ProjectDetailsAllOfDataCoverage**](ProjectDetailsAllOfDataCoverage.md)> |  | [optional]
**search_console** | Option<[**models::ProjectDetailsAllOfSearchConsole**](ProjectDetailsAllOfSearchConsole.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


