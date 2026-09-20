# \ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_project**](ProjectsApi.md#create_project) | **POST** /projects | Create a project (fast mode)
[**create_project_draft**](ProjectsApi.md#create_project_draft) | **POST** /project_drafts | Start a project draft (wizard step 1)
[**finalize_project_draft**](ProjectsApi.md#finalize_project_draft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project
[**get_project_details**](ProjectsApi.md#get_project_details) | **GET** /dimensions/projects/{id} | Project details
[**get_project_draft**](ProjectsApi.md#get_project_draft) | **GET** /project_drafts/{id} | Read a project draft
[**list_locales**](ProjectsApi.md#list_locales) | **GET** /dimensions/locales | List locales with data
[**list_models**](ProjectsApi.md#list_models) | **GET** /dimensions/models | List models with data
[**list_projects**](ProjectsApi.md#list_projects) | **GET** /dimensions/projects | List projects
[**update_project**](ProjectsApi.md#update_project) | **PATCH** /projects/{id} | Update a project profile (Brand Book)
[**update_project_draft**](ProjectsApi.md#update_project_draft) | **PATCH** /project_drafts/{id} | Submit a wizard step



## create_project

> models::ProjectCreateResponse create_project(project_create_request)
Create a project (fast mode)

Create a complete project in one call: project fields, prompts (queued for execution and categorization), competitors, weekly email subscription. Idempotent via `external_identifier` (embed-enabled accounts only; replay returns 200 with the existing project). Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_create_request** | [**ProjectCreateRequest**](ProjectCreateRequest.md) |  | [required] |

### Return type

[**models::ProjectCreateResponse**](ProjectCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_project_draft

> create_project_draft(create_project_draft_request)
Start a project draft (wizard step 1)

Start the multi-step project-creation wizard. Returns a draft_id plus AI suggestions (name, description, industry, brand aliases) for the URL. Cold URLs can take up to ~2 minutes to analyze; pass suggest=false to skip AI and respond instantly. Drafts expire after 24h. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_project_draft_request** | [**CreateProjectDraftRequest**](CreateProjectDraftRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## finalize_project_draft

> finalize_project_draft(id, finalize_project_draft_request)
Finalize a draft into a real project

Creates the project with all accumulated draft data (same effects as POST /projects). Idempotent: finalizing an already-finalized draft returns 200 with the existing project. Optional overrides: weekly_email_subscribed, execute_prompts_immediately.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **String** |  | [required] |
**finalize_project_draft_request** | Option<[**FinalizeProjectDraftRequest**](FinalizeProjectDraftRequest.md)> |  |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_project_details

> models::ProjectDetails get_project_details(id)
Project details

Detailed info for one project: matching_names, industry, business model, primary products, target audience, brand voice, locale, app store IDs, stats (incl. prompts_by_brand_kind counts) and data_coverage (models, countries and languages with data).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** |  | [required] |

### Return type

[**models::ProjectDetails**](ProjectDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_project_draft

> get_project_draft(id, include_suggestions)
Read a project draft

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **String** | Draft id (draft_...) | [required] |
**include_suggestions** | Option<**bool**> | Cache-only: returns suggestions for the current step if already generated, never triggers AI |  |[default to false]

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_locales

> list_locales(project_id)
List locales with data

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_models

> list_models(project_id)
List models with data

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_projects

> models::ListProjects200Response list_projects(output)
List projects

All projects accessible with your API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::ListProjects200Response**](listProjects_200_response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_project

> update_project(id, update_project_request)
Update a project profile (Brand Book)

Updates the project profile, the same fields as Project Settings: brand_name, description, industry, business_model (plus business_model_other when it is OTHER), target_audience, brand_voice, goals, primary_products, matching_names. Send only the fields to change; unknown fields are rejected. All seven Brand Book fields feed every GEO Writer task and prompt suggestions; only industry, description, and target_audience help Recommendations. A matching_names change re-runs mention/citation matching over the project history in the background (rematching=true); further edits are rejected while that runs. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** |  | [required] |
**update_project_request** | [**UpdateProjectRequest**](UpdateProjectRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_project_draft

> update_project_draft(id, update_project_draft_request)
Submit a wizard step

Submit one step (details, prompts, competitors, owned_media). Strict forward gating: a step is only accepted when every previous step is complete (`ERR_DRAFT_STATE` otherwise); completed steps can be resubmitted. Responds with the updated draft plus AI suggestions for the next step.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **String** |  | [required] |
**update_project_draft_request** | [**UpdateProjectDraftRequest**](UpdateProjectDraftRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

