# SearchConsolePropertiesResponseDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**String**> | Property id, the value the property parameter takes, e.g. sc-domain:example.com | [optional]
**name** | Option<**String**> |  | [optional]
**primary** | Option<**bool**> | The property read when the property parameter is omitted | [optional]
**r#type** | Option<**Type**> |  (enum: domain, url_prefix) | [optional]
**status** | Option<**Status**> |  (enum: connected, reconnect_required) | [optional]
**last_synced_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


