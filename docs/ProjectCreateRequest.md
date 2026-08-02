# ProjectCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**website_url** | **String** | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. | 
**name** | **String** |  | 
**main_country** | **String** |  | 
**main_language** | **String** |  | 
**brand_name** | Option<**String**> |  | [optional]
**description** | Option<**String**> |  | [optional]
**industry** | Option<**Vec<String>**> |  | [optional]
**matching_names** | Option<**Vec<String>**> |  | [optional]
**prompts** | Option<**Vec<String>**> |  | [optional]
**competitors** | Option<[**Vec<models::ProjectCreateRequestCompetitorsInner>**](ProjectCreateRequestCompetitorsInner.md)> |  | [optional]
**owned_media** | Option<[**models::ProjectCreateRequestOwnedMedia**](ProjectCreateRequestOwnedMedia.md)> |  | [optional]
**use_subdomain** | Option<**bool**> |  | [optional][default to false]
**weekly_email_subscribed** | Option<**bool**> |  | [optional][default to false]
**external_identifier** | Option<**String**> | Embed-enabled (Enterprise) accounts only; other accounts receive ERR_PLAN_REQUIRED. Idempotency key and embed-session join key, unique per account | [optional]
**execute_prompts_immediately** | Option<**bool**> |  | [optional][default to true]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


