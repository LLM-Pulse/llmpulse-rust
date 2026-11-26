# QueryFanOutRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query_text** | Option<**String**> | The sub-query a model issued (view=query) | [optional]
**count** | Option<**i32**> | Times it was issued (view=query) | [optional]
**share** | Option<**f64**> | Share of all sub-query occurrences, on a 0-100 scale (view=query) | [optional]
**prompt_id** | Option<**i32**> | view=prompt | [optional]
**prompt_text** | Option<**String**> | view=prompt | [optional]
**variations_count** | Option<**i32**> | Distinct sub-queries issued for the prompt (view=prompt) | [optional]
**total_count** | Option<**i32**> | Sub-queries issued for the prompt, repeats included (view=prompt) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


