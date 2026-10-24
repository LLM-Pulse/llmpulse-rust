# RecommendationItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**recommendation_id** | **i32** |  | 
**recommendation_type** | **String** |  | 
**category** | **String** |  | 
**title** | **String** |  | 
**description** | Option<**String**> |  | [optional]
**priority** | **Priority** |  (enum: high, medium, low) | 
**estimated_impact** | Option<**String**> |  | [optional]
**action_items** | **Vec<String>** |  | 
**source_refs** | **Vec<String>** | Evidence codes (e.g. P1, C2) resolved in resolved_source_refs | 
**status** | **Status** |  (enum: active, completed, archived) | 
**status_changed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**position** | **i32** |  | 
**metadata** | Option<**std::collections::HashMap<String, serde_json::Value>**> | Free-form details. Carries effort (low, medium or high) when the generator rated it, archive_reason (not_relevant, too_complex or competitor) on an item archived with a reason, and domain on PR & Citation Building items. | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**resolved_source_refs** | Option<**Vec<std::collections::HashMap<String, serde_json::Value>>**> | The evidence each source_refs code points to (prompt, citation or own page) | [optional]
**unresolved_source_refs** | Option<**Vec<String>**> | Present only when a code points to no stored evidence | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


