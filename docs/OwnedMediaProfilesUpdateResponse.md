# OwnedMediaProfilesUpdateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**platforms** | Option<[**Vec<models::OwnedMediaPlatformProfiles>**](OwnedMediaPlatformProfiles.md)> |  | [optional]
**settings** | Option<[**models::OwnedMediaProfileSettings**](OwnedMediaProfileSettings.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]
**updated_fields** | Option<**Vec<String>**> | The fields this request set | [optional]
**profile_scrapes_queued** | Option<**Vec<String>**> | Platforms whose new profile is being scraped in the background for its name and avatar | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


