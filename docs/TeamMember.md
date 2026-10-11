# TeamMember

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**email** | **String** |  | 
**name** | Option<**String**> |  | [optional]
**role** | **Role** | The account owner is listed first; everyone else who joined is a member. (enum: owner, member) | 
**status** | **Status** | A blocked member cannot sign in or use the API until unblocked in the app. (enum: active, blocked) | 
**permission_role** | Option<**String**> | Access level of a member: full_access, view_only, custom or account_role. Null for the owner. | 
**account_role** | Option<[**models::TeamAccountRole**](TeamAccountRole.md)> |  | 
**permissions** | Option<[**std::collections::HashMap<String, Vec<String>>**](Vec.md)> | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. | 
**account_admin** | **bool** | A co-owner, who can manage the team. | 
**billing_access** | **bool** | Can open Billing and Plans (always true for the owner). | 
**all_projects** | **bool** | Has access to every project of the account, including future ones. | 
**project_ids** | **Vec<i32>** | The projects a member is limited to; empty when all_projects is true. | 
**last_sign_in_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**joined_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the member accepted the invitation; null for the owner and for members added without one. | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


