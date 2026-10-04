# GetAccount200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**plan** | Option<**String**> | Plan key (starter, growth, scale, ...). Absent for a key limited to some projects. | [optional]
**plan_name** | Option<**String**> | Display name of the plan to show people (e.g. Scale++ for the scaleplusplus key). Absent for a key limited to some projects. | [optional]
**tracking_frequency** | Option<**String**> | How often prompts run (weekly, daily, monthly, ...) | [optional]
**role** | Option<**Role**> | Whether the key belongs to the account owner or a team member (enum: owner, member) | [optional]
**api_key_project_ids** | Option<**Vec<i32>**> | The projects the calling API key is limited to; null for a key that sees the whole account, and for OAuth | [optional]
**subscription** | Option<[**models::GetAccount200ResponseSubscription**](GetAccount200ResponseSubscription.md)> |  | [optional]
**limits** | Option<[**models::GetAccount200ResponseLimits**](GetAccount200ResponseLimits.md)> |  | [optional]
**rate_limits** | Option<[**models::GetAccount200ResponseRateLimits**](GetAccount200ResponseRateLimits.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


