# ProjectDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**name** | Option<**String**> | Internal project label (sidebar, settings, admin) | [optional]
**brand_name** | Option<**String**> | LLM-facing brand label (used in prompts and customer-facing charts). Defaults to `name` when not set. | [optional]
**url** | Option<**String**> |  | [optional]
**description** | Option<**String**> |  | [optional]
**matching_names** | Option<**Vec<String>**> |  | [optional]
**industry** | Option<**String**> |  | [optional]
**business_model** | Option<**String**> |  | [optional]
**primary_products** | Option<**String**> |  | [optional]
**target_audience** | Option<**String**> |  | [optional]
**brand_voice** | Option<**String**> |  | [optional]
**country_code** | Option<**String**> |  | [optional]
**language_code** | Option<**String**> |  | [optional]
**paused** | Option<**bool**> |  | [optional]
**google_play_id** | Option<**String**> |  | [optional]
**app_store_id** | Option<**String**> |  | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**stats** | Option<[**models::ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


