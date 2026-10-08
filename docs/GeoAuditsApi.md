# \GeoAuditsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**compare_geo_audit_runs**](GeoAuditsApi.md#compare_geo_audit_runs) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs
[**create_geo_audits**](GeoAuditsApi.md#create_geo_audits) | **POST** /geo_audits | Create GEO audits
[**delete_geo_audit**](GeoAuditsApi.md#delete_geo_audit) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit
[**get_geo_audit**](GeoAuditsApi.md#get_geo_audit) | **GET** /geo_audits/{id} | Get a GEO audit
[**get_geo_audit_run**](GeoAuditsApi.md#get_geo_audit_run) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run
[**list_geo_alerts**](GeoAuditsApi.md#list_geo_alerts) | **GET** /geo_alerts | List GEO audit alerts
[**list_geo_audit_findings**](GeoAuditsApi.md#list_geo_audit_findings) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run
[**list_geo_audit_issues**](GeoAuditsApi.md#list_geo_audit_issues) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit
[**list_geo_audit_runs**](GeoAuditsApi.md#list_geo_audit_runs) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit
[**list_geo_audits**](GeoAuditsApi.md#list_geo_audits) | **GET** /geo_audits | List GEO audits
[**run_geo_audit**](GeoAuditsApi.md#run_geo_audit) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now
[**update_geo_audit**](GeoAuditsApi.md#update_geo_audit) | **PATCH** /geo_audits/{id} | Update a GEO audit
[**update_geo_audit_issue**](GeoAuditsApi.md#update_geo_audit_issue) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue



## compare_geo_audit_runs

> models::GeoAuditComparison compare_geo_audit_runs(project_id, id, from_run, to_run)
Compare two GEO audit runs

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**id** | **String** | Audit id | [required] |
**from_run** | Option<**i32**> | Run number to compare from (default the run before to_run) |  |
**to_run** | Option<**i32**> | Run number to compare to (default the latest completed run) |  |

### Return type

[**models::GeoAuditComparison**](GeoAuditComparison.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_geo_audits

> models::GeoAuditCreateResponse create_geo_audits(geo_audit_create_request)
Create GEO audits

Creates one audit per entry of audit_types and starts the first run of each (it counts against the manual run limits: 6 per audit per hour, 200 per account per day). cadence weekly or monthly is accepted only for types whose checks are tracked run to run, and counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Creating an audit that was archived restores it with its history. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**geo_audit_create_request** | [**GeoAuditCreateRequest**](GeoAuditCreateRequest.md) |  | [required] |

### Return type

[**models::GeoAuditCreateResponse**](GeoAuditCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_geo_audit

> models::GeoAuditArchived delete_geo_audit(project_id, id)
Delete (archive) a GEO audit

Archives the audit. Requires a `read_write` scope API key and, for team members, delete permission on GEO Optimization.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**id** | **String** | Audit id | [required] |

### Return type

[**models::GeoAuditArchived**](GeoAuditArchived.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_geo_audit

> models::GeoAuditResponse get_geo_audit(project_id, id)
Get a GEO audit

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**id** | **String** | Audit id | [required] |

### Return type

[**models::GeoAuditResponse**](GeoAuditResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_geo_audit_run

> models::GeoAuditRunDetail get_geo_audit_run(project_id, geo_audit_id, sequence)
Get a GEO audit run

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**geo_audit_id** | **String** | Audit id | [required] |
**sequence** | **i32** | Run number within the audit | [required] |

### Return type

[**models::GeoAuditRunDetail**](GeoAuditRunDetail.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_geo_alerts

> models::GeoAlertList list_geo_alerts(project_id, audit_id, page, per_page)
List GEO audit alerts

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**audit_id** | Option<**String**> | Only alerts of this audit |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]

### Return type

[**models::GeoAlertList**](GeoAlertList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_geo_audit_findings

> models::GeoAuditFindingList list_geo_audit_findings(project_id, geo_audit_id, sequence, page, per_page, output)
List the findings of a GEO audit run

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**geo_audit_id** | **String** | Audit id | [required] |
**sequence** | **i32** | Run number within the audit | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::GeoAuditFindingList**](GeoAuditFindingList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_geo_audit_issues

> models::GeoAuditIssueList list_geo_audit_issues(project_id, geo_audit_id, state, page, per_page)
List the issues of a GEO audit

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**geo_audit_id** | **String** | Audit id | [required] |
**state** | Option<**String**> | open means open and not accepted; default all |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]

### Return type

[**models::GeoAuditIssueList**](GeoAuditIssueList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_geo_audit_runs

> models::GeoAuditRunList list_geo_audit_runs(project_id, geo_audit_id, page, per_page, output)
List the runs of a GEO audit

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**geo_audit_id** | **String** | Audit id | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::GeoAuditRunList**](GeoAuditRunList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_geo_audits

> models::GeoAuditList list_geo_audits(project_id, audit_type, status, cadence, page, per_page)
List GEO audits

Lists the project's audits, most recently updated first. Archived audits are left out unless status=archived.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**audit_type** | Option<**String**> |  |  |
**status** | Option<**String**> |  |  |
**cadence** | Option<**String**> |  |  |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]

### Return type

[**models::GeoAuditList**](GeoAuditList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## run_geo_audit

> models::GeoAuditRunResponse run_geo_audit(project_id, geo_audit_id)
Run a GEO audit now

Starts a run and returns it with status queued; poll GET /geo_audits/{geo_audit_id}/runs/{sequence} until status is completed, failed or unreachable. Limited to 6 manual runs per audit per rolling hour and 200 per account per day (ERR_LIMIT_REACHED); scheduled runs do not count. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**geo_audit_id** | **String** | Audit id | [required] |

### Return type

[**models::GeoAuditRunResponse**](GeoAuditRunResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_geo_audit

> models::GeoAuditResponse update_geo_audit(id, geo_audit_update_request)
Update a GEO audit

Updates the schedule, the email alerts or the status. Making an audit recurring or resuming it counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Requires a `read_write` scope API key and, for team members, update permission on GEO Optimization.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **String** | Audit id | [required] |
**geo_audit_update_request** | [**GeoAuditUpdateRequest**](GeoAuditUpdateRequest.md) |  | [required] |

### Return type

[**models::GeoAuditResponse**](GeoAuditResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_geo_audit_issue

> models::GeoAuditIssueResponse update_geo_audit_issue(geo_audit_id, id, geo_audit_issue_update_request)
Accept or reopen a GEO audit issue

Requires a `read_write` scope API key and, for team members, update permission on GEO Optimization.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**geo_audit_id** | **String** | Audit id | [required] |
**id** | **i32** | Issue id | [required] |
**geo_audit_issue_update_request** | [**GeoAuditIssueUpdateRequest**](GeoAuditIssueUpdateRequest.md) |  | [required] |

### Return type

[**models::GeoAuditIssueResponse**](GeoAuditIssueResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

