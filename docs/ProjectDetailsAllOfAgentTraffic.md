# ProjectDetailsAllOfAgentTraffic

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | Option<**Status**> |  (enum: connected, reconnect_required, imported, not_connected) | [optional]
**provider** | Option<**String**> | The connected source (e.g. cloudflare_graphql, bunny_cdn, s3 or the log drain's provider), null without a live source | [optional]
**connect_url** | Option<**String**> | The in-app Agent Analytics page, where a source is connected or reconnected | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


