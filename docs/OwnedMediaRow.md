# OwnedMediaRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | Option<**chrono::NaiveDate**> | The start date of the actual reporting period (view=activity) | [optional]
**entity_id** | Option<**String**> | Platform entity identifier (view=activity) | [optional]
**entity_name** | Option<**String**> | Current entity name when known (view=activity) | [optional]
**entity_url** | Option<**String**> | Current profile, channel or app listing URL when known (view=activity) | [optional]
**store** | Option<**Store**> | Store selected for provider=mobile_apps (view=activity) (enum: google_play, app_store) | [optional]
**competitor_id** | Option<**i32**> | Competitor identifier when the activity row represents a competitor app | [optional]
**title** | Option<**String**> |  | [optional]
**url** | Option<**String**> |  | [optional]
**channel_name** | Option<**String**> |  | [optional]
**channel_handle** | Option<**String**> | The video's channel handle, without the @ | [optional]
**channel_url** | Option<**String**> |  | [optional]
**video_id** | Option<**String**> |  | [optional]
**key** | Option<**String**> | The channel key (handle:..., channel:... or name:...), accepted as profile by /dimensions/owned_media/citing_prompts | [optional]
**name** | Option<**String**> |  | [optional]
**handle** | Option<**String**> |  | [optional]
**caption** | Option<**String**> |  | [optional]
**owner_handle** | Option<**String**> |  | [optional]
**thumbnail_url** | Option<**String**> | The post or video image. Our cached copy where one exists, so the link does not expire | [optional]
**avatar_url** | Option<**String**> | The profile or channel image. Our cached copy where one exists | [optional]
**content_type** | Option<**String**> | The post format on its platform: reel, post or tv on Instagram, post or pulse on LinkedIn, post elsewhere | [optional]
**citations** | Option<**i32**> | Citations for the row; for view=activity, the count in this reporting period | [optional]
**unique_videos** | Option<**i32**> |  | [optional]
**unique_posts** | Option<**i32**> |  | [optional]
**followers** | Option<**i32**> |  | [optional]
**likes** | Option<**i32**> |  | [optional]
**comments** | Option<**i32**> |  | [optional]
**views** | Option<**serde_json::Value**> | View count as the platform reports it, a number or a numeric string, or null when unknown | [optional]
**published_at** | Option<**String**> | Publication date as the platform reports it | [optional]
**posted_at** | Option<**String**> | Publication date as the platform reports it (ISO 8601, or Unix seconds on TikTok) | [optional]
**avg_position** | Option<**f64**> | Average position of the citation in the answers (1 = first); null when unknown | [optional]
**yours** | Option<**bool**> |  | [optional]
**citation_date** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**position** | Option<**i32**> |  | [optional]
**model** | Option<**String**> |  | [optional]
**domain** | Option<**String**> | The app's store listing URL (provider=mobile_apps) | [optional]
**total_responses** | Option<**i32**> |  | [optional]
**rank** | Option<**i32**> |  | [optional]
**global_rank** | Option<**i32**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


