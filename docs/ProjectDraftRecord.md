# ProjectDraftRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**draft_id** | **String** | Draft id (draft_...) | 
**status** | **String** | open, finalized or expired | 
**current_step** | **String** | The next step to submit (details, prompts, competitors, owned_media), or ready when the draft can be finalized | 
**steps_completed** | **Vec<String>** |  | 
**steps_remaining** | **Vec<String>** | Required steps not submitted yet | 
**optional_steps** | **Vec<String>** | Steps the plan allows but finalize does not require (owned_media from Growth) | 
**finalizable** | **bool** |  | 
**website_url** | **String** |  | 
**main_country** | **String** |  | 
**main_language** | **String** |  | 
**use_subdomain** | **bool** |  | 
**name** | Option<**String**> | Null until the details step | 
**brand_name** | Option<**String**> |  | 
**description** | Option<**String**> |  | 
**industry** | **Vec<String>** |  | 
**matching_names** | **Vec<String>** |  | 
**prompts** | **Vec<String>** |  | 
**competitors** | [**Vec<models::ProjectDraftRecordCompetitorsInner>**](ProjectDraftRecordCompetitorsInner.md) |  | 
**owned_media** | [**models::ProjectDraftRecordOwnedMedia**](ProjectDraftRecordOwnedMedia.md) |  | 
**weekly_email_subscribed** | **bool** |  | 
**external_identifier** | Option<**String**> |  | 
**execute_prompts_immediately** | **bool** |  | 
**project_id** | Option<**i32**> | The project the draft became; null until finalized | 
**expires_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


