# Competitor

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**name** | Option<**String**> |  | [optional]
**domain** | Option<**String**> | Bare (scheme-less) domain. Null only on the own-brand row (include_project_brand=true) when the project has no URL. | [optional]
**actor_type** | Option<**ActorType**> | Only present when include_project_brand=true (enum: project, competitor) | [optional]
**is_own** | Option<**bool**> | Only present when include_project_brand=true | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


