# AccountAgentUsage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**percent_used** | Option<**i32**> | Whole percent used, rounded down, from 0 to 100; 100 means the allowance is spent and new questions wait until resets_on. null when unlimited is true | [optional]
**unlimited** | Option<**bool**> |  | [optional]
**included** | Option<**bool**> | Whether the plan includes the in-app AI assistant. false on a plan without it, where percent_used is 100 | [optional]
**period** | Option<**String**> | Always month | [optional]
**resets_on** | Option<**chrono::NaiveDate**> | The first day of next month, when the allowance starts again | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


