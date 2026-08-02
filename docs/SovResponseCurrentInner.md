# SovResponseCurrentInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actor** | Option<[**models::Actor**](Actor.md)> |  | [optional]
**share** | Option<**f64**> |  | [optional]
**previous_share** | Option<**f64**> | The actor's share in the last complete bucket before the current one; null without complete history. | [optional]
**avg_share** | Option<**f64**> | Mean share across complete buckets with data (partial buckets excluded); null without complete history. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


