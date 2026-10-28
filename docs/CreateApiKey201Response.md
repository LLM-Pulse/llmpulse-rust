# CreateApiKey201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**name** | **String** |  | 
**prefix** | **String** | The visible start of the token, to recognize the key. Never the secret itself. | 
**scope** | **Scope** |  (enum: read, read_write) | 
**project_scoped** | **bool** | True when the key is limited to project_ids; false for an account-wide key. | 
**project_ids** | **Vec<i32>** | The projects the key is limited to; empty for an account-wide key. | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**last_used_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Updated at most once a minute. | 
**revoked_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | 
**token** | **String** | The secret to send as Bearer token. Shown only in this response. | 
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


