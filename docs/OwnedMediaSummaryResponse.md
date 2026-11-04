# OwnedMediaSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**provider** | Option<**String**> |  | [optional]
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**connected** | Option<**bool**> | Whether a profile is claimed on the platform (on overview, on any platform) | [optional]
**kpis** | Option<[**models::OwnedMediaKpis**](OwnedMediaKpis.md)> |  | [optional]
**previous** | Option<[**models::OwnedMediaSummaryResponsePrevious**](OwnedMediaSummaryResponsePrevious.md)> |  | [optional]
**changes** | Option<[**models::OwnedMediaKpiChanges**](OwnedMediaKpiChanges.md)> |  | [optional]
**weekly** | Option<[**Vec<models::OwnedMediaWeek>**](OwnedMediaWeek.md)> |  | [optional]
**by_model** | Option<[**Vec<models::OwnedMediaModelShare>**](OwnedMediaModelShare.md)> | Null for provider=overview | [optional]
**by_country** | Option<[**Vec<models::OwnedMediaCountryShare>**](OwnedMediaCountryShare.md)> | Null for provider=overview | [optional]
**content_types** | Option<[**Vec<models::OwnedMediaContentTypeShare>**](OwnedMediaContentTypeShare.md)> | Social and YouTube providers only | [optional]
**age_buckets** | Option<[**Vec<models::OwnedMediaAgeBucketShare>**](OwnedMediaAgeBucketShare.md)> | Social and YouTube providers only. Posts or videos without a known publication date are left out | [optional]
**stores** | Option<[**Vec<models::OwnedMediaStoreTotals>**](OwnedMediaStoreTotals.md)> | provider=mobile_apps only | [optional]
**platforms** | Option<[**Vec<models::OwnedMediaPlatformRollup>**](OwnedMediaPlatformRollup.md)> | provider=overview only, one row per platform the caller can read | [optional]
**activity** | Option<[**Vec<models::OwnedMediaSummaryActivityPeriod>**](OwnedMediaSummaryActivityPeriod.md)> | All providers. One row per actual project reporting period with runs; provider=overview has null yours and other, and provider=reddit also returns positive, neutral and negative sentiment counts. Citation counts use the selected date window, and periods with runs but no citation have zero | [optional]
**subreddit_activity** | Option<[**Vec<models::RedditSubredditActivityPeriod>**](RedditSubredditActivityPeriod.md)> | provider=reddit only. One row per subreddit and actual reporting period; the top five subreddits are separate and Others has a null subreddit | [optional]
**positions** | Option<[**Vec<models::RedditPositionShare>**](RedditPositionShare.md)> | provider=reddit only. Position distribution over the selected date window | [optional]
**brand_share** | Option<[**Vec<models::RedditBrandShare>**](RedditBrandShare.md)> | provider=reddit only. Citation share among the tracked brand and competitors with cited mentions | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


