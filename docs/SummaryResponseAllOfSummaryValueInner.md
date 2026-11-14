# SummaryResponseAllOfSummaryValueInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actor** | Option<[**models::Actor**](Actor.md)> |  | [optional]
**metric** | Option<**String**> |  | [optional]
**total** | Option<**f64**> | Count metrics sum the buckets; rate, position and sentiment metrics average them. ai_visibility_score (weighted_visibility) is the window's points divided by its data days (the days with responses under the filters), the number the app shows, whatever the granularity. | [optional]
**aggregation** | Option<**Aggregation**> | How total combines the buckets (average for ai_visibility_score, a per-data-day score) (enum: sum, average) | [optional]
**min** | Option<**f64**> |  | [optional]
**max** | Option<**f64**> |  | [optional]
**last** | Option<**f64**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


