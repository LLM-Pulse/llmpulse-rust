# GetAccount200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**plan** | Option<**String**> | Plan key (starter, growth, scale, ...) | [optional]
**tracking_frequency** | Option<**String**> | How often prompts run (weekly, daily, monthly, ...) | [optional]
**role** | Option<**Role**> | Whether the key belongs to the account owner or a team member (enum: owner, member) | [optional]
**subscription** | Option<[**models::GetAccount200ResponseSubscription**](GetAccount200ResponseSubscription.md)> |  | [optional]
**limits** | Option<[**models::GetAccount200ResponseLimits**](GetAccount200ResponseLimits.md)> |  | [optional]
**rate_limits** | Option<[**models::GetAccount200ResponseRateLimits**](GetAccount200ResponseRateLimits.md)> |  | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


