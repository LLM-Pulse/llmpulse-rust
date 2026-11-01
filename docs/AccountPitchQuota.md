# AccountPitchQuota

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**limit** | Option<**i32**> |  | [optional]
**used** | Option<**i32**> |  | [optional]
**remaining** | Option<**i32**> |  | [optional]
**unlimited** | Option<**bool**> |  | [optional]
**period** | Option<**String**> | Always month | [optional]
**resets_on** | Option<**chrono::NaiveDate**> | The first day of next month, when the allowance starts again | [optional]
**access** | Option<**Access**> | Whether the account may create pitch projects. The account owner or an account admin (co-owner) requests access in Account Settings > Pitch projects and our team reviews it; approved access goes dormant while the account is below the Scale tier, on a trial, has a payment problem, is set to cancel or has an allowance of 0 (enum: none, pending, approved, dormant, rejected, revoked) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


