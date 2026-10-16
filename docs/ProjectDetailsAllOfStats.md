# ProjectDetailsAllOfStats

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**prompts_count** | Option<**i32**> | Active prompts in the project | [optional]
**prompts_available** | Option<**i32**> | Prompts that can still be added to this project, the lower of its free slots under prompt_limit and the prompts left in the account quota; null when neither caps it | [optional]
**prompts_by_brand_kind** | Option<[**models::ProjectDetailsAllOfStatsPromptsByBrandKind**](ProjectDetailsAllOfStatsPromptsByBrandKind.md)> |  | [optional]
**competitors_count** | Option<**i32**> |  | [optional]
**collections_count** | Option<**i32**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


