# ProjectCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project** | Option<**serde_json::Value**> | Same shape as GET /dimensions/projects/{id} | [optional]
**prompts** | Option<[**models::ProjectCreateResponsePrompts**](ProjectCreateResponsePrompts.md)> |  | [optional]
**competitors** | Option<[**models::ProjectCreateResponseCompetitors**](ProjectCreateResponseCompetitors.md)> |  | [optional]
**email_subscription** | Option<[**models::ProjectCreateResponseEmailSubscription**](ProjectCreateResponseEmailSubscription.md)> |  | [optional]
**limits** | Option<[**models::ProjectCreateResponseLimits**](ProjectCreateResponseLimits.md)> |  | [optional]
**idempotent** | Option<**bool**> | Present and true only on external_identifier replays | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


