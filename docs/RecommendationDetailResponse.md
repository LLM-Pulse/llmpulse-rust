# RecommendationDetailResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**project_id** | **i32** |  | 
**recommendation_type** | **RecommendationType** |  (enum: ai_visibility, social_community, brand_building, sentiment_reputation) | 
**status** | **Status** |  (enum: pending, processing, completed, failed) | 
**error_message** | Option<**String**> | Set only when status is failed | 
**generated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Null until the generation completes | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**total_recommendations** | **i32** |  | 
**high_priority_count** | **i32** |  | 
**summary** | [**models::RecommendationDetailResponseSummary**](RecommendationDetailResponseSummary.md) |  | 
**context** | **serde_json::Value** | Generation context and run diagnostics as stored; empty until the generation completes. Its keys are not a stable contract | 
**report_data** | **std::collections::HashMap<String, serde_json::Value>** | The stored run, including the evidence indices (prompts_index, citations_index, own_content_index and others) that the source_refs codes of the items point to. Its keys are not a stable contract | 
**item_counts** | [**models::RecommendationDetailResponseItemCounts**](RecommendationDetailResponseItemCounts.md) |  | 
**items** | [**Vec<models::RecommendationItem>**](RecommendationItem.md) |  | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


