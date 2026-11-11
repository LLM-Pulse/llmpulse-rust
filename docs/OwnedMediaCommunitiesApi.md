# \OwnedMediaCommunitiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_owned_media_profiles**](OwnedMediaCommunitiesApi.md#get_owned_media_profiles) | **GET** /projects/{id}/owned_media | Get a project's owned-media profiles
[**get_owned_media_summary**](OwnedMediaCommunitiesApi.md#get_owned_media_summary) | **GET** /dimensions/owned_media/summary | Get an owned-media summary
[**list_owned_media**](OwnedMediaCommunitiesApi.md#list_owned_media) | **GET** /dimensions/owned_media | List owned-media citations
[**list_owned_media_citing_prompts**](OwnedMediaCommunitiesApi.md#list_owned_media_citing_prompts) | **GET** /dimensions/owned_media/citing_prompts | List the answers citing an owned-media item
[**list_reddit_citations**](OwnedMediaCommunitiesApi.md#list_reddit_citations) | **GET** /dimensions/reddit | List cited Reddit content
[**update_owned_media_profiles**](OwnedMediaCommunitiesApi.md#update_owned_media_profiles) | **PATCH** /projects/{id}/owned_media | Update a project's owned-media profiles



## get_owned_media_profiles

> models::OwnedMediaProfilesResponse get_owned_media_profiles(id)
Get a project's owned-media profiles

The profiles whose citations count as yours in the Owned Media and YouTube Intelligence reports, as Project Settings > Brand channels shows them. platforms holds one entry per platform with whether it is connected, how many extra profiles it accepts and its profiles: the main one, the extra ones, and on Reddit the claimed subreddits and usernames, each with its URL, handle, store (for apps), name, avatar and the state of the scrape that reads them. settings holds the current value of every field PATCH accepts, ready to edit and send back. Requires the Growth plan or above.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** | Project ID | [required] |

### Return type

[**models::OwnedMediaProfilesResponse**](OwnedMediaProfilesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_owned_media_summary

> models::OwnedMediaSummaryResponse get_owned_media_summary(project_id, provider, model, collection_id, country_code, language_code, brand_kind, range, from, to)
Get an owned-media summary

The numbers behind one Owned Media tab. kpis gives platform citations (total), yours (the account's own profiles and content), your_profile and your_content separately where available, and share_pct; previous gives the same KPIs for the period of the same length that ends just before from, and changes gives the difference (percent for counts, percentage points for share_pct and positive_pct, null when there is nothing to compare). weekly remains the Monday-anchored series. Every provider returns activity by actual project reporting period, with date at the period start, citations, yours and other; yours and other are null for provider=overview. The overview also includes each readable platform's activity under platforms, with date and citations. Periods without runs are omitted, and a period with runs but no citation has zero. Activity counts use the selected date window. by_model and by_country split citations; content_types (reel, post, tv, pulse, or regular, shorts and live on YouTube) and age_buckets cover posts and videos. provider=mobile_apps adds stores and per-store totals; provider=trustpilot counts trustpilot.com citations, yours being those of the profile of the account's own domains; provider=overview returns one rollup per readable platform. provider=reddit adds unique_subreddits, unique_authors, positive_pct, and positive, neutral and negative sentiment counts in activity for the citing AI answers, plus subreddit_activity for the top five subreddits and Others, positions and brand_share. A team member also needs the YouTube Intelligence permission for provider=youtube or Reddit Intelligence for provider=reddit. Defaults to the last 30 days. Requires the Growth plan or above.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**provider** | **String** | The platform to summarize, or overview for every platform at once | [required] |
**model** | Option<**String**> | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |

### Return type

[**models::OwnedMediaSummaryResponse**](OwnedMediaSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_owned_media

> models::OwnedMediaListResponse list_owned_media(project_id, provider, page, per_page, view, store, owned, model, collection_id, country_code, language_code, brand_kind, range, from, to, output)
List owned-media citations

Which owned-media content AI answers cite, by platform. `provider` is required. Each row carries a `yours` flag so you can compare your own presence against everyone else cited on the same platform. Video, post, channel and profile rows also carry their image (thumbnail_url or avatar_url, our cached copy where one exists), their average position in the answers and, on YouTube, the video id, the channel handle and URL, and the channel key that /dimensions/owned_media/citing_prompts accepts. `view=activity` returns one row per entity and actual reporting period; periods without runs are omitted, while a run without a citation has a real zero. Its citation counts cover the selected date window; profile, channel and app metadata are current values, not historical growth. For provider=mobile_apps, select the store with `store`. For provider=trustpilot, `view=profiles` (the default) lists the cited Trustpilot profiles with their rating and review count, `view=brands` the brand and each competitor with their profile's rating, its change since the previous monthly read, review count, read status and citations, and `view=reviews` the reviews published in the window on those profiles; ratings and reviews come from a monthly read of each profile. `view=own_citations` returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/owned_media/summary?provider=reddit for the summary and /dimensions/reddit for cited-content tables. A team member also needs the YouTube Intelligence permission for provider=youtube. Requires the Growth plan or above.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**provider** | **String** | The platform to report on | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**view** | Option<**String**> | Row shape; the allowed set depends on provider, and activity is available for each provider |  |
**store** | Option<**String**> | provider=mobile_apps only |  |[default to google_play]
**owned** | Option<**bool**> | Return only rows belonging to the account's own connected profile |  |
**model** | Option<**String**> | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::OwnedMediaListResponse**](OwnedMediaListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_owned_media_citing_prompts

> models::OwnedMediaCitingPromptsResponse list_owned_media_citing_prompts(project_id, provider, page, per_page, url, profile, model, collection_id, country_code, language_code, brand_kind, range, from, to, output)
List the answers citing an owned-media item

The drill-down behind one row of an Owned Media or YouTube Intelligence table. Pass exactly one of url (a post or video URL, any variant of it) or profile (a handle with or without @, a profile or channel URL, or the channel key the YouTube channels rows return). item describes it (title, image, owner, whether it is yours and its stats), citation_count and prompt_count count its citations in the window, and data lists the citing answers newest first, each with its prompt, answer id, model, country, language, execution date, a plain-text excerpt and its link in the app. It shows prompt and answer text, so a team member also needs the Prompts permission, and YouTube Intelligence for provider=youtube. Defaults to the last 30 days. Requires the Growth plan or above.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**provider** | **String** | The platform the item belongs to | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**url** | Option<**String**> | A post or video URL, or a profile or channel URL. Exclusive with profile |  |
**profile** | Option<**String**> | A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url |  |
**model** | Option<**String**> | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

[**models::OwnedMediaCitingPromptsResponse**](OwnedMediaCitingPromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_reddit_citations

> list_reddit_citations(project_id, page, per_page, view, subreddit, author, status, owned, brand, order, direction, model, collection_id, country_code, language_code, brand_kind, range, from, to, output)
List cited Reddit content

Which Reddit content AI answers cite for your tracked prompts. view=subreddits (default) returns one row per subreddit with its citation count, unique authors and positive/negative sentiment split; view=authors returns one row per author; view=threads returns the individual cited threads with upvotes, comments, average position and dominant sentiment. view=breakdowns returns the figures behind Reddit Intelligence > Sentiment and breakdowns: citations is the number of Reddit citations after the filters, and each row is one slice, with breakdown (sentiment, model or country), key, count and pct, the share within its breakdown as the page charts it. Sentiment is that of the AI answer that cited Reddit, with all five labels (very_positive to very_negative) listed, zero included; order and direction do not apply. Requires the Growth plan or above.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**view** | Option<**String**> |  |  |[default to subreddits]
**subreddit** | Option<**String**> | Filter to one subreddit (name without the r/ prefix) |  |
**author** | Option<**String**> | Filter to one Reddit author |  |
**status** | Option<**String**> | view=threads only |  |
**owned** | Option<**bool**> | Return only subreddits/authors the account has claimed as its own |  |
**brand** | Option<**String**> | Filter to citations whose scraped Reddit content mentions a brand: 'brand' for the tracked brand, or a competitor id. Reads the page content, not the AI answer. |  |
**order** | Option<**String**> | Sort field; the allowed set depends on view, and view=breakdowns accepts none |  |
**direction** | Option<**String**> |  |  |[default to desc]
**model** | Option<**String**> | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. |  |
**collection_id** | Option<**String**> | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. |  |
**country_code** | Option<**String**> | One ISO country code or a comma-separated list (e.g. US,GB,DE) |  |
**language_code** | Option<**String**> | One ISO language code or a comma-separated list (e.g. en,es,de) |  |
**brand_kind** | Option<**String**> | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. |  |
**range** | Option<**i32**> | Number of days to look back (alternative to from/to) |  |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |

### Return type

 (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_owned_media_profiles

> models::OwnedMediaProfilesUpdateResponse update_owned_media_profiles(id, update_owned_media_profiles_request)
Update a project's owned-media profiles

Sets the profiles whose citations count as yours, like Project Settings > Brand channels. Send only the fields to change: a URL field takes a URL, or an empty string or null to clear it, and every list REPLACES the stored one ([] clears it). URLs are normalized like the app (a profile URL is stored in its canonical form, a Google Play package name becomes its listing URL), and anything the app would refuse (a URL from another platform, an extra profile equal to the main one, more than 10 extra profiles, a malformed subreddit) is rejected with ERR_INVALID_PARAM and nothing is applied. A new main or extra profile is scraped in the background for its name and avatar, listed in profile_scrapes_queued. The response is the GET payload after the change. A team member needs the Owned Media create permission, YouTube Intelligence create to change the YouTube channel, and Projects update to change the extra profile or Reddit lists. Requires the Growth plan or above and a `read_write` scope API key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **i32** | Project ID | [required] |
**update_owned_media_profiles_request** | [**UpdateOwnedMediaProfilesRequest**](UpdateOwnedMediaProfilesRequest.md) |  | [required] |

### Return type

[**models::OwnedMediaProfilesUpdateResponse**](OwnedMediaProfilesUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

