# AccountExecutionQuota

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**limit** | Option<**i32**> |  | [optional]
**used** | Option<**i32**> |  | [optional]
**remaining** | Option<**i32**> |  | [optional]
**unlimited** | Option<**bool**> |  | [optional]
**period** | Option<**Period**> | The tracking window, from the account's tracking cadence (week runs Monday to Sunday) (enum: day, week, month) | [optional]
**resets_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the next window starts and the allowance is full again (00:00 Europe/Madrid) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


