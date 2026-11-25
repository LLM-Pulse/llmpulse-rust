# OwnedMediaKpis

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total** | Option<**i32**> | Citations of the platform in the window, yours and everyone else's | [optional]
**yours** | Option<**i32**> | Citations of your own profiles and their content | [optional]
**your_profile** | Option<**i32**> | Citations of your profile or channel pages. Null for mobile_apps and overview | [optional]
**your_content** | Option<**i32**> | Citations of your posts or videos. Null for mobile_apps and overview | [optional]
**share_pct** | Option<**f64**> | yours as a percentage of total (0-100) | [optional]
**unique_subreddits** | Option<**i32**> | Number of cited subreddits (provider=reddit; null or omitted for other providers) | [optional]
**unique_authors** | Option<**i32**> | Number of cited Reddit authors (provider=reddit; null or omitted for other providers) | [optional]
**positive_pct** | Option<**f64**> | Positive sentiment among rated Reddit citations, as a percentage (provider=reddit; null or omitted for other providers) | [optional]
**connected_count** | Option<**i32**> | provider=overview only. The platforms with a connected profile, channel or app, out of the rows in platforms (the Connected sources card). It describes the current setup, so previous.kpis and changes leave it out | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


