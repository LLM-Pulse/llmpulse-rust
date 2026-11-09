# CmsPublication

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**platform** | Option<**Platform**> |  (enum: wordpress) | [optional]
**site_url** | Option<**String**> |  | [optional]
**status** | Option<**Status**> | queued and sending are on their way; unknown means a send timed out and the next attempt looks the draft up before creating one; drafted carries remote_id and edit_url; failed carries error_code (enum: queued, sending, unknown, drafted, failed) | [optional]
**title** | Option<**String**> |  | [optional]
**slug** | Option<**String**> |  | [optional]
**source_url** | Option<**String**> | For an update task, the page the draft revises | [optional]
**remote_id** | Option<**i32**> | WordPress post id of the draft | [optional]
**remote_status** | Option<**String**> | WordPress status of the post when the draft was created (draft) | [optional]
**remote_url** | Option<**String**> |  | [optional]
**edit_url** | Option<**String**> | The post's edit screen in the WordPress admin | [optional]
**error_code** | Option<**String**> | Why the send failed, the same token as error.meta.reason, for example reconnect_required, authorization_header_lost, missing_capability, firewall_blocked, timeout, unreachable or rejected | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**sent_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


