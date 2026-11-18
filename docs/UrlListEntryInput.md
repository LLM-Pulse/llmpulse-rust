# UrlListEntryInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**value** | **String** | An exact URL, a \"host/path/_*\" prefix or a domain. | 
**match_type** | Option<**MatchType**> |  (enum: url, prefix, domain) | [optional]
**added_on** | Option<**chrono::NaiveDate**> | When the URL was published or bought. Default today. | [optional]
**cost** | Option<**f64**> | What the URL cost, in the list currency. | [optional]
**channel** | Option<**String**> | Where it came from, such as a marketplace or PR agency. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


