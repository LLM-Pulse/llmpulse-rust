# \TeamApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_team_invitation**](TeamApi.md#create_team_invitation) | **POST** /team_invitations | Invite a team member
[**list_team_invitations**](TeamApi.md#list_team_invitations) | **GET** /team_invitations | List pending team invitations
[**list_team_members**](TeamApi.md#list_team_members) | **GET** /team_members | List team members
[**remove_team_member**](TeamApi.md#remove_team_member) | **DELETE** /team_members/{id} | Remove a team member
[**revoke_team_invitation**](TeamApi.md#revoke_team_invitation) | **DELETE** /team_invitations/{id} | Revoke a pending team invitation



## create_team_invitation

> models::CreateTeamInvitation201Response create_team_invitation(create_team_invitation_request)
Invite a team member

Invites someone to the account team with the same rules as the Team Members settings page, and sends them the invitation email (email_sent is false when the email provider refused it; the invitation still exists, so revoke it and invite again once the address is fixed). Send project_ids, or all_projects: true for every project (for a team member inviting, every project they can access). The account owner and co-owners choose the access with permission_role: full_access (default), view_only, custom (with permissions, feature key to verbs) or account_role (with account_role_id). A team member with permission to invite cannot choose access: leave those fields out and the invitation copies their own permissions. Only the account owner can set account_admin (co-owner) or billing_access. An address already registered on the platform, or with an invitation pending, is refused with ERR_INVALID_PARAM (revoke the pending one first). An account that cannot add more team members, or that reached its daily limit of invitations sent through the API and MCP (revoked ones count), answers ERR_LIMIT_REACHED; the message says which. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_team_invitation_request** | [**CreateTeamInvitationRequest**](CreateTeamInvitationRequest.md) |  | [required] |

### Return type

[**models::CreateTeamInvitation201Response**](createTeamInvitation_201_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_team_invitations

> models::ListTeamInvitations200Response list_team_invitations(page, per_page)
List pending team invitations

Lists invitations that have not been accepted yet: the address, the access and projects the person will get, when the invitation was sent and when its link expires. An accepted invitation keeps its id and moves to GET /team_members. Same access rules as GET /team_members.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> |  |  |
**per_page** | Option<**i32**> | Default 20, max 100 |  |

### Return type

[**models::ListTeamInvitations200Response**](listTeamInvitations_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_team_members

> models::ListTeamMembers200Response list_team_members(page, per_page)
List team members

Lists the account owner first, then every team member who joined, with their access level (permission_role, account role and the resulting permissions), co-owner and billing flags, project access, status (active or blocked) and last sign-in. Pending invitations are listed by GET /team_invitations; GET /account limits.team_members.used counts both. Available to the account owner, co-owners and team members with the Team Members permission. A key limited to some projects answers ERR_KEY_PROJECT_SCOPED: the team belongs to the whole account.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> |  |  |
**per_page** | Option<**i32**> | Default 20, max 100 |  |

### Return type

[**models::ListTeamMembers200Response**](listTeamMembers_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## remove_team_member

> models::RemoveTeamMember200Response remove_team_member(id)
Remove a team member

Removes a member from the team, as the settings page does: their sessions and API keys stop working at once and their user account is deleted in the background shortly after. Account owner or co-owner only; a co-owner cannot remove the owner, another co-owner or themselves. The owner cannot be removed. Pending invitations are revoked with DELETE /team_invitations/{id}; an id that is not a member of the account answers ERR_NOT_FOUND. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** | The member id from GET /team_members | [required] |

### Return type

[**models::RemoveTeamMember200Response**](removeTeamMember_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## revoke_team_invitation

> models::RevokeTeamInvitation200Response revoke_team_invitation(id)
Revoke a pending team invitation

Revokes a pending invitation: its link stops working immediately. Account owner or co-owner only, and a co-owner cannot revoke an invitation that makes someone a co-owner. Members who already joined are removed with DELETE /team_members/{id}; an id that is not a pending invitation of the account answers ERR_NOT_FOUND. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** | The invitation id from GET /team_invitations | [required] |

### Return type

[**models::RevokeTeamInvitation200Response**](revokeTeamInvitation_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

