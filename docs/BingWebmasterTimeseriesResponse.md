# BingWebmasterTimeseriesResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**site** | Option<**String**> | The connected site, as Bing Webmaster Tools names it (e.g. https://example.com/) | [optional]
**sync_status** | Option<**String**> | State of the daily sync: pending, syncing, completed, failed or on_hold (the data already synced still answers, but stops updating until the site is reconnected) | [optional]
**last_synced_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the site last synced. Null before its first sync, or while history_current is false. | [optional]
**history_current** | Option<**bool**> | False right after the site was changed and before its first sync. Until then data is empty and data_through is null. | [optional]
**from** | Option<**chrono::NaiveDate**> |  | [optional]
**to** | Option<**chrono::NaiveDate**> |  | [optional]
**data_through** | Option<**chrono::NaiveDate**> | The last day synced for the site. Later days are missing, not zero. | [optional]
**granularity** | Option<**String**> |  | [optional]
**data** | Option<[**Vec<models::BingWebmasterTimeseriesResponseDataInner>**](BingWebmasterTimeseriesResponseDataInner.md)> | One bucket per day, week (starting Monday) or month that has synced days. Days without data are left out, not reported as zero. | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


