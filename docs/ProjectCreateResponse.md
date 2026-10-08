# ProjectCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**draft_id** | Option<**String**> | The finalized draft; only present on POST /project_drafts/{id}/finalize | [optional]
**project** | Option<**serde_json::Value**> | Same shape as GET /dimensions/projects/{id} | [optional]
**prompts** | Option<[**models::ProjectCreateResponsePrompts**](ProjectCreateResponsePrompts.md)> |  | [optional]
**competitors** | Option<[**models::ProjectCreateResponseCompetitors**](ProjectCreateResponseCompetitors.md)> |  | [optional]
**collections** | Option<[**Vec<models::ProjectCreateResponseCollectionsInner>**](ProjectCreateResponseCollectionsInner.md)> | Collections created from the request's collections field (empty when none were sent; absent on an idempotent replay) | [optional]
**same_domain_projects** | Option<[**Vec<models::ProjectCreateResponseSameDomainProjectsInner>**](ProjectCreateResponseSameDomainProjectsInner.md)> | Projects the caller can already see on the same domain (absent on an idempotent replay). Informational only: the create is never blocked, since one domain tracked per market is a normal setup. | [optional]
**email_subscription** | Option<[**models::ProjectCreateResponseEmailSubscription**](ProjectCreateResponseEmailSubscription.md)> |  | [optional]
**limits** | Option<[**models::ProjectCreateResponseLimits**](ProjectCreateResponseLimits.md)> |  | [optional]
**idempotent** | Option<**bool**> | Present and true only on external_identifier replays | [optional]
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


