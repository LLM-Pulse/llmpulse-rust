# UpdateProjectDraftRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**step** | **Step** |  (enum: details, prompts, competitors, owned_media) | 
**name** | Option<**String**> |  | [optional]
**brand_name** | Option<**String**> |  | [optional]
**description** | Option<**String**> |  | [optional]
**industry** | Option<**Vec<String>**> |  | [optional]
**matching_names** | Option<**Vec<String>**> | Brand-name variants used to detect mentions (details step). At most 50 names of up to 100 characters each; the step stores the list as sent, and finalize refuses a longer list or name with ERR_INVALID_PARAM (422) | [optional]
**external_identifier** | Option<**String**> |  | [optional]
**prompts** | Option<**Vec<String>**> |  | [optional]
**competitors** | Option<**Vec<serde_json::Value>**> | Competitors step: objects {domain, brand_name, matching_names}, capped by plan. Each competitor's matching_names takes at most 50 names of up to 100 characters, checked at finalize like POST /projects | [optional]
**youtube_channel_url** | Option<**String**> |  | [optional]
**instagram_profile_url** | Option<**String**> |  | [optional]
**facebook_page_url** | Option<**String**> |  | [optional]
**tiktok_profile_url** | Option<**String**> |  | [optional]
**app_store_url** | Option<**String**> |  | [optional]
**google_play_url** | Option<**String**> |  | [optional]
**suggest** | Option<**bool**> |  | [optional][default to true]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


