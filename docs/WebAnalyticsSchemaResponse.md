# WebAnalyticsSchemaResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | Option<**i32**> |  | [optional]
**provider** | Option<**Provider**> | The connected web analytics provider. (enum: google_analytics, adobe_analytics, matomo, posthog, plausible, piano) | [optional]
**property** | Option<**String**> | The property, site, report suite (rsid:...), data view (dataview:...) or project every query runs on. | [optional]
**query_language** | Option<**String**> | The native query format the provider accepts. | [optional]
**docs_url** | Option<**String**> | The provider's reference for that format. | [optional]
**allowed_fields** | Option<**Vec<String>**> | Top-level query fields that are forwarded. | [optional]
**rules** | Option<**Vec<String>**> | What the bridge enforces and the provider's main constraints. | [optional]
**example** | Option<**std::collections::HashMap<String, serde_json::Value>**> | A worked query to adapt. | [optional]
**fields** | Option<**std::collections::HashMap<String, serde_json::Value>**> | The provider's live field list where it offers one: GA4 dimensions and metrics with custom definitions, Adobe ids, Matomo report methods, PostHog event names, the Plausible catalog. Null when the provider did not return it. | [optional]
**fields_unavailable** | Option<**String**> | Present when the field list could not be read; the format and example still apply. | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


