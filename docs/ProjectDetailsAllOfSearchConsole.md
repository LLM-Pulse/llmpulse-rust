# ProjectDetailsAllOfSearchConsole

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | Option<**Status**> |  (enum: connected, reconnect_required, not_connected) | [optional]
**property** | Option<**String**> | The primary property (e.g. sc-domain:example.com), null when not connected | [optional]
**connect_url** | Option<**String**> | The in-app page where the property is connected or reconnected (Preferences > Project Settings > Data Connections) | [optional]
**properties_count** | Option<**i32**> | Connected properties Google still accepts (reconnect_required ones excluded); GET /search_console/properties lists every property with its status | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


