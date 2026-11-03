# SearchConsoleAiVisibilityGapsResponseDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | Option<**String**> |  | [optional]
**impressions** | Option<**i32**> |  | [optional]
**clicks** | Option<**i32**> |  | [optional]
**ctr** | Option<**f64**> | 0..1 fraction | [optional]
**position** | Option<**f64**> | Impression-weighted average position | [optional]
**prompt_id** | Option<**i32**> | The project's prompt with the same text as the query; null when no prompt matches | [optional]
**responses** | Option<**i32**> | AI answers the matching prompt got in the window over the account's enabled models; null when no prompt matches | [optional]
**brand_visibility** | Option<**f64**> | Brand Visibility of the matching prompt in the window, percent (0-100) of its AI answers that mention the brand, over the account's enabled models; null when no prompt matches or it has no answer | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


