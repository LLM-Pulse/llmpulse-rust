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
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


