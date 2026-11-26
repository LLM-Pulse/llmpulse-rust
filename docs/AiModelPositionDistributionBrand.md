# AiModelPositionDistributionBrand

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **String** | project or competitor | 
**id** | **i32** | Project id, or competitor id | 
**competitor_id** | Option<**i32**> | Null for the project, the competitor id otherwise | 
**name** | **String** |  | 
**domain** | Option<**String**> | Bare (scheme-less) domain. Null for the project when it has no URL. | 
**buckets** | [**Vec<models::AiModelPositionDistributionBrandBucketsInner>**](AiModelPositionDistributionBrandBucketsInner.md) | One per position bucket, in order: position_1, position_2_3, position_4_7 and position_8_plus | 
**max_stacked_value** | **i32** | The brand's largest mentions count of one period, its buckets added up | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


