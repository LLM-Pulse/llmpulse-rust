# SummaryResponseAllOfSummaryValueInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actor** | Option<[**models::Actor**](Actor.md)> |  | [optional]
**metric** | Option<**String**> |  | [optional]
**total** | Option<**f64**> | Count metrics sum the buckets. Rate, position and sentiment metrics pool the whole window, the number the app shows for the same filters, whatever the granularity; visibility is all mentions over all responses x 100, citation_rate all citations over all responses x 100, a sentiment share all verdicts of that kind over all verdicts x 100, an average position the average of every position recorded in the window. They are never a mean of the bucket values. ai_visibility_score (weighted_visibility) is the window's points divided by its tracking runs (the days, weeks or months at the account's tracking frequency with responses under the filters). | [optional]
**aggregation** | Option<**Aggregation**> | How total combines the buckets. sum for counts; average for rates, positions and sentiment, pooled over the window, and for ai_visibility_score, a per-run score (enum: sum, average) | [optional]
**min** | Option<**f64**> |  | [optional]
**max** | Option<**f64**> |  | [optional]
**last** | Option<**f64**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


