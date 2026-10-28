# \ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_project**](ProjectsApi.md#create_project) | **POST** /projects | Create a project (fast mode)
[**create_project_draft**](ProjectsApi.md#create_project_draft) | **POST** /project_drafts | Start a project draft (wizard step 1)
[**delete_project**](ProjectsApi.md#delete_project) | **DELETE** /projects/{id} | Delete a project
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

Create a complete project in one call: project fields, prompts (queued for execution and categorization), collections tagging those prompts, competitors, weekly email subscription. The response lists same_domain_projects so an accidental duplicate is visible; it never blocks the create. Idempotent via `external_identifier` (embed-enabled accounts only; replay returns 200 with the existing project). Requires a `read_write` scope API key.

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


## delete_project

> models::ProjectDeleteResponse delete_project(id)
Delete a project

Deletes a project, like Delete Project in Project Settings, and cannot be undone. The project disappears at once from the app, GET /dimensions/projects and every other endpoint, and frees a project slot; a background job then deletes its prompts, answers, mentions, citations, sentiment, competitors and metrics history. API keys limited to it lose it, and a key left with no project is revoked. A project that is already being deleted, or that the key cannot see, answers ERR_PROJECT_NOT_FOUND. Requires an account-wide `read_write` scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. A team member needs permission to delete projects.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** |  | [required] |

### Return type

[**models::ProjectDeleteResponse**](ProjectDeleteResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
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

Detailed info for one project: matching_names, additional_owned_domains, industry, business model, primary products, target audience, brand voice, locale, app store IDs, prompt_limit (the project's own prompt cap, null without one), stats (incl. prompts_by_brand_kind counts and prompts_available, how many prompts can still be added: the lower of the project's free slots and the account's remaining prompts, null when neither caps it), data_coverage (models, countries and languages with data) and the status of each data connection (search_console, ai_traffic, agent_traffic) with the connect_url where the user connects it.

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

> models::LocalesResponse list_locales(project_id)
List locales with data

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |

### Return type

[**models::LocalesResponse**](LocalesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_models

> models::ModelsResponse list_models(project_id)
List models with data

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |

### Return type

[**models::ModelsResponse**](ModelsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

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

> models::ProjectUpdateResponse update_project(id, update_project_request)
Update a project profile (Brand Book)

Updates the project name and profile, the same fields as Project Settings: name, brand_name, description, industry, business_model (plus business_model_other when it is OTHER), target_audience, brand_voice, goals, primary_products, matching_names, and the additional owned domains (additional_owned_domains). Send only the fields to change; unknown fields are rejected, and a request is applied whole or not at all. All seven Brand Book fields feed every GEO Writer task and prompt suggestions; only industry, description, and target_audience help Recommendations. A matching_names change re-runs mention/citation matching over the project history in the background, and an additional_owned_domains change reprocesses the past answers that cite an added or removed domain (rematching=true); further edits are rejected while that runs. Only the account owner can send additional_owned_domains: a team member key gets ERR_INSUFFICIENT_PERMISSION and nothing is applied. prompt_limit sets or (null) removes the project's own prompt cap, as in Account Settings > Prompt Limits. Only the account owner or a co-owner whose permissions grant Projects update can send it (Account Settings > Prompt Limits lets any co-owner change it; here a co-owner, like every team member, also needs Projects update): any other team member gets ERR_INSUFFICIENT_PERMISSION, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with nothing applied. A request that sends only prompt_limit is applied even while a rematch runs. Requires a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** |  | [required] |
**update_project_request** | [**UpdateProjectRequest**](UpdateProjectRequest.md) |  | [required] |

### Return type

[**models::ProjectUpdateResponse**](ProjectUpdateResponse.md)

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

