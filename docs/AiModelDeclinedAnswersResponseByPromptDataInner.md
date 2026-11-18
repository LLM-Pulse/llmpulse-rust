# AiModelDeclinedAnswersResponseByPromptDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**answers** | Option<**i32**> | Finished runs of the model, declined ones included | [optional]
**declined** | Option<**i32**> | Answers the model declined | [optional]
**decline_rate** | Option<**f64**> |  | [optional]
**safety_filter** | Option<**i32**> | Answers declined by the model's own safety filters | [optional]
**safety_filter_rate** | Option<**f64**> |  | [optional]
**topic_refusal** | Option<**i32**> | Answers that declined the topic itself, such as tobacco, gambling or alcohol | [optional]
**topic_refusal_rate** | Option<**f64**> |  | [optional]
**prompt_id** | Option<**i32**> |  | [optional]
**prompt_text** | Option<**String**> |  | [optional]
**last_declined_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the prompt's latest declined answer of the window was created; null when none was declined | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


