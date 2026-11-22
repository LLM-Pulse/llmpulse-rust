# ProjectDetailsAllOfBingWebmaster

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | Option<**Status**> |  (enum: connected, reconnect_required, not_connected) | [optional]
**site** | Option<**String**> | The connected site (e.g. https://example.com/), null when not connected | [optional]
**last_synced_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When that site last synced, null before its first sync | [optional]
**connect_url** | Option<**String**> | The in-app page where the site is connected or reconnected (Preferences > Project Settings > Connections) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


