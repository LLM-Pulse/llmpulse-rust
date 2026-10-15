# UpdateOwnedMediaProfilesRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**youtube_channel_url** | Option<**String**> | The main YouTube channel URL (@handle, /channel/UC..., /c/... or /user/...). An empty string or null clears it | [optional]
**app_store_url** | Option<**String**> | The App Store app URL, with its id number. An empty string or null clears it | [optional]
**google_play_url** | Option<**String**> | The Google Play app URL, or its package name (com.acme.app). An empty string or null clears it | [optional]
**instagram_profile_url** | Option<**String**> | The main Instagram profile URL. An empty string or null clears it | [optional]
**facebook_page_url** | Option<**String**> | The main Facebook Page URL. An empty string or null clears it | [optional]
**tiktok_profile_url** | Option<**String**> | The main TikTok profile URL. An empty string or null clears it | [optional]
**linkedin_company_url** | Option<**String**> | The main LinkedIn Company Page URL (/company/...). An empty string or null clears it | [optional]
**youtube_extra_profile_urls** | Option<**Vec<String>**> | FULL replacement list of extra YouTube channel URLs (at most 10); [] clears it | [optional]
**mobile_apps_extra_profile_urls** | Option<**Vec<String>**> | FULL replacement list of extra App Store or Google Play app URLs (at most 10); [] clears it | [optional]
**instagram_extra_profile_urls** | Option<**Vec<String>**> | FULL replacement list of extra Instagram profile URLs (at most 10); [] clears it | [optional]
**facebook_extra_profile_urls** | Option<**Vec<String>**> | FULL replacement list of extra Facebook Page URLs (at most 10); [] clears it | [optional]
**tiktok_extra_profile_urls** | Option<**Vec<String>**> | FULL replacement list of extra TikTok profile URLs (at most 10); [] clears it | [optional]
**linkedin_extra_profile_urls** | Option<**Vec<String>**> | FULL replacement list of extra LinkedIn Company Page URLs (at most 10); [] clears it | [optional]
**reddit_subreddits** | Option<**Vec<String>**> | FULL replacement list (at most 10) of subreddit names the brand owns, without r/; [] clears it | [optional]
**reddit_usernames** | Option<**Vec<String>**> | FULL replacement list (at most 25) of Reddit usernames the brand owns, without u/; [] clears it | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


