# CreateTeamInvitationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**email** | **String** |  | 
**project_ids** | Option<**Vec<i32>**> | Projects the member can access. Send this or all_projects true. | [optional]
**all_projects** | Option<**bool**> | Access to every project, including future ones | [optional]
**permission_role** | Option<**PermissionRole**> | Default full_access. Owner and co-owners only. (enum: full_access, view_only, custom, account_role) | [optional]
**account_role_id** | Option<**i32**> | One of the account's roles, with permission_role account_role | [optional]
**permissions** | Option<[**std::collections::HashMap<String, Vec<String>>**](Vec.md)> | With permission_role custom: feature key to the verbs granted (read, create, update, delete), for example {\"overview\": [\"read\"], \"prompts\": [\"read\", \"create\"]} | [optional]
**account_admin** | Option<**bool**> | Make the member a co-owner. Account owner only. | [optional]
**billing_access** | Option<**bool**> | Access to Billing and Plans. Account owner only. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


