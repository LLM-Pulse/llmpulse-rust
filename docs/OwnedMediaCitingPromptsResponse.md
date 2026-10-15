# OwnedMediaCitingPromptsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**provider** | Option<**String**> |  | [optional]
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**item** | Option<[**models::OwnedMediaCitedItem**](OwnedMediaCitedItem.md)> |  | [optional]
**citation_count** | Option<**i32**> | Citations of the item in the window | [optional]
**prompt_count** | Option<**i32**> | Distinct prompts whose answers cited it | [optional]
**page** | Option<**i32**> |  | [optional]
**per_page** | Option<**i32**> |  | [optional]
**total** | Option<**i32**> | Citing answers | [optional]
**data** | Option<[**Vec<models::OwnedMediaCitingAnswer>**](OwnedMediaCitingAnswer.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


