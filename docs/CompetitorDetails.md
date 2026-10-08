# CompetitorDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**i32**> |  | [optional]
**project_id** | Option<**i32**> |  | [optional]
**brand_name** | Option<**String**> |  | [optional]
**domain** | Option<**String**> |  | [optional]
**matching_names** | Option<**Vec<String>**> |  | [optional]
**google_play_id** | Option<**String**> |  | [optional]
**app_store_id** | Option<**String**> |  | [optional]
**citation_match_mode** | Option<[**models::CitationMatchMode**](CitationMatchMode.md)> |  | [optional]
**citation_match_path** | Option<**String**> | Set only when citation_match_mode is path_prefix | [optional]
**google_play_name** | Option<**String**> | English app name on Google Play, when the competitor has an Android app | [optional]
**app_store_name** | Option<**String**> | English app name on the App Store, when the competitor has an iOS app | [optional]
**google_play_icon_url** | Option<**String**> |  | [optional]
**app_store_icon_url** | Option<**String**> |  | [optional]
**color** | Option<**String**> |  | [optional]
**processing** | Option<**bool**> | True while the competitor's historical mentions are being recalculated | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


