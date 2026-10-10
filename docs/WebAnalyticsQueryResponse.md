# WebAnalyticsQueryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**provider** | Option<**Provider**> |  (enum: google_analytics, adobe_analytics, matomo, posthog, plausible, piano) | [optional]
**property** | Option<**String**> |  | [optional]
**columns** | Option<[**Vec<models::WebAnalyticsQueryResponseColumnsInner>**](WebAnalyticsQueryResponseColumnsInner.md)> |  | [optional]
**rows** | Option<[**Vec<Vec<serde_json::Value>>**](Vec.md)> | One array per row, values in column order: strings, numbers or null. | [optional]
**row_count** | Option<**i32**> | Rows in this response (at most 5,000). | [optional]
**total_rows** | Option<**i32**> | Rows the provider has for the query, when it reports it. | [optional]
**truncated** | Option<**bool**> | True when the provider has more rows than returned; page with its own offset or page field. | [optional]
**totals** | Option<**std::collections::HashMap<String, serde_json::Value>**> | Metric totals by metric name, when the query asked for them. | [optional]
**notes** | Option<**Vec<String>**> | Provider caveats: sampling, thresholds, more rows available. | [optional]
**meta** | Option<**std::collections::HashMap<String, serde_json::Value>**> | Provider metadata such as GA4 time zone, currency and remaining property quota. | [optional]
**fetched_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the provider answered. | [optional]
**cached** | Option<**bool**> | True when the answer came from the 10-minute cache instead of the provider. | [optional]
**query** | Option<**std::collections::HashMap<String, serde_json::Value>**> | The request as sent to the provider, with the connected property forced and limits applied. | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


