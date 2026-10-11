# CreateTeamInvitation201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** | Kept by the member once they accept, when they move to GET /team_members. | 
**email** | **String** |  | 
**permission_role** | **PermissionRole** |  (enum: full_access, view_only, custom, account_role) | 
**account_role** | Option<[**models::TeamAccountRole**](TeamAccountRole.md)> |  | 
**permissions** | Option<[**std::collections::HashMap<String, Vec<String>>**](Vec.md)> | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. | 
**account_admin** | **bool** |  | 
**billing_access** | **bool** |  | 
**all_projects** | **bool** |  | 
**project_ids** | **Vec<i32>** |  | 
**invited_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the invitation email was last sent. | [optional]
**expires_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the invitation link stops working. | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**email_sent** | **bool** | False when the email provider refused the invitation email | 
**request_id** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


