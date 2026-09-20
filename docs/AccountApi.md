# \AccountApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_account**](AccountApi.md#get_account) | **GET** /account | Account plan, quota usage and rate limits



## get_account

> models::GetAccount200Response get_account()
Account plan, quota usage and rate limits

Returns the account plan, tracking cadence, subscription window, how much of each quota is used (prompts, projects, competitors per project, monthly GEO Writer tasks, team members) and the published API rate limits. Limits resolve through the account owner, so a team member sees the capacity that applies to them. An unlimited quota returns limit and remaining as null with unlimited set to true, since Infinity is not representable in JSON. The subscription block is only present for callers who can access Billing and Plans in the app (the account owner, or a team member with billing access); everyone else gets the same response without that key. requests_per_minute is the ceiling of the key used for the call, not a fixed number.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetAccount200Response**](getAccount_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

