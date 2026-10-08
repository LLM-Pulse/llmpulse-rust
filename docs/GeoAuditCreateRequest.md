# GeoAuditCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**target** | **String** | The domain (site-wide types) or page URL to audit | 
**audit_types** | **Vec<AuditTypes>** | One or more audit types; each becomes its own audit and starts its first run (enum: agent_readiness, robots_txt, crawlability, schema, content_readiness, discoverability, site_structure) | 
**cadence** | Option<**Cadence**> | once (default), weekly or monthly. Weekly and monthly need a type whose checks are tracked and count against the plan limit of recurring audits (enum: once, weekly, monthly) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


