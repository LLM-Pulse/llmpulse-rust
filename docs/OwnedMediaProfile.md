# OwnedMediaProfile

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | Option<**String**> |  | [optional]
**handle** | Option<**String**> | The handle, page id, store app id, subreddit or username | [optional]
**kind** | Option<**Kind**> |  (enum: profile, app, subreddit, username) | [optional]
**main** | Option<**bool**> | True for the main profile of its platform (or store), false for an extra one | [optional]
**store** | Option<**String**> | google_play or app_store for an app; null elsewhere | [optional]
**name** | Option<**String**> |  | [optional]
**avatar_url** | Option<**String**> |  | [optional]
**scrape_status** | Option<**String**> | State of the profile scrape that reads its name and avatar: pending, running, ready, failed or skipped; null when none has started or the platform has none | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


