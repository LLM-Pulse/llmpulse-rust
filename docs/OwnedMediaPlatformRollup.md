# OwnedMediaPlatformRollup

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider** | Option<**Provider**> |  (enum: youtube, mobile_apps, instagram, facebook, tiktok, linkedin, trustpilot, reddit) | [optional]
**connected** | Option<**bool**> |  | [optional]
**total** | Option<**i32**> |  | [optional]
**yours** | Option<**i32**> |  | [optional]
**share_pct** | Option<**f64**> |  | [optional]
**weekly** | Option<[**Vec<models::OwnedMediaPlatformRollupWeeklyInner>**](OwnedMediaPlatformRollupWeeklyInner.md)> |  | [optional]
**activity** | Option<[**Vec<models::OwnedMediaPlatformActivityPeriod>**](OwnedMediaPlatformActivityPeriod.md)> | One date/citation row per project tracking period that holds a run inside the window; a period whose runs all fell before from is left out | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


