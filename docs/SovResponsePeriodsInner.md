# SovResponsePeriodsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | Option<**chrono::NaiveDate**> |  | [optional]
**mentions** | Option<**i32**> |  | [optional]
**partial** | Option<**bool**> |  | [optional]
**confidence** | Option<**String**> | How far the shares of this period can be trusted, from its mentions: none (0), low (under 30), medium (under 100) or high (100 or more). | [optional]
**margin_of_error** | Option<**f64**> | Worst-case 95% margin of a share in percentage points, 98 / sqrt(mentions); mentions within one answer are not independent, so the real margin is at least this wide. null with no mentions. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


