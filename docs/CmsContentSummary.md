# CmsContentSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> | WordPress post or page id | [optional]
**r#type** | Option<**Type**> |  (enum: post, page) | [optional]
**status** | Option<**String**> | WordPress status (publish, future, draft, pending or private) | [optional]
**slug** | Option<**String**> |  | [optional]
**title** | Option<**String**> | Plain-text title as the site renders it | [optional]
**url** | Option<**String**> | The public link on the connected site; null when the site names a link on another host | [optional]
**modified_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


