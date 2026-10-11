# \SearchConsoleApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_search_console_pages**](SearchConsoleApi.md#get_search_console_pages) | **GET** /search_console/pages | Top Search Console pages (Growth+)
[**get_search_console_queries**](SearchConsoleApi.md#get_search_console_queries) | **GET** /search_console/queries | Top Search Console queries (Growth+)
[**get_search_console_rows**](SearchConsoleApi.md#get_search_console_rows) | **GET** /search_console/rows | Search Console rows by several dimensions (Growth+)
[**get_search_console_summary**](SearchConsoleApi.md#get_search_console_summary) | **GET** /search_console/summary | Search Console summary (Growth+)
[**get_search_console_timeseries**](SearchConsoleApi.md#get_search_console_timeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+)



## get_search_console_pages

> models::SearchConsoleListResponse get_search_console_pages(project_id, range, from, to, sort, page, per_page, start_row, output, search_type, filters, data_state, aggregation_type)
Top Search Console pages (Growth+)

Top Google Search Console landing pages over a date range, ranked by impressions, clicks, ctr or position, paginated. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, and start_row reads the next block. Page rows are counted per page rather than per property, so they can differ from the totals. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**u32**> | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention. |  |
**from** | Option<**chrono::NaiveDate**> | Start date (YYYY-MM-DD). Defaults to 30 days ago. |  |
**to** | Option<**chrono::NaiveDate**> | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. |  |
**sort** | Option<**String**> |  |  |[default to impressions]
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**start_row** | Option<**u32**> | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. |  |[default to 0]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |
**search_type** | Option<**String**> | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. |  |[default to web]
**filters** | Option<**String**> | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. |  |
**data_state** | Option<**String**> | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. |  |[default to final]
**aggregation_type** | Option<**String**> | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. |  |[default to auto]

### Return type

[**models::SearchConsoleListResponse**](SearchConsoleListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_search_console_queries

> models::SearchConsoleListResponse get_search_console_queries(project_id, range, from, to, sort, page, per_page, start_row, output, search_type, filters, data_state, aggregation_type)
Top Search Console queries (Growth+)

Top Google Search Console search queries over a date range, ranked by impressions, clicks, ctr or position, paginated. Excludes anonymized queries; for headline totals use /search_console/summary. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, so the rows add up to less than the totals, and start_row reads the next block. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**u32**> | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention. |  |
**from** | Option<**chrono::NaiveDate**> | Start date (YYYY-MM-DD). Defaults to 30 days ago. |  |
**to** | Option<**chrono::NaiveDate**> | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. |  |
**sort** | Option<**String**> |  |  |[default to impressions]
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**start_row** | Option<**u32**> | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. |  |[default to 0]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |
**search_type** | Option<**String**> | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. |  |[default to web]
**filters** | Option<**String**> | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. |  |
**data_state** | Option<**String**> | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. |  |[default to final]
**aggregation_type** | Option<**String**> | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. |  |[default to auto]

### Return type

[**models::SearchConsoleListResponse**](SearchConsoleListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_search_console_rows

> models::SearchConsoleRowsResponse get_search_console_rows(project_id, dimensions, range, from, to, sort, page, per_page, start_row, output, search_type, filters, data_state, aggregation_type)
Search Console rows by several dimensions (Growth+)

Google Search Console rows grouped by 1 to 3 dimensions (date, country, device, page, query, searchAppearance) over a date range, each row carrying its dimension values as fields plus impressions, clicks, ctr (0..1) and position, ranked by impressions, clicks, ctr or position, paginated. Google ranks rows by clicks and returns at most 25,000 per request (truncated: true when reached); start_row moves that window. Query rows exclude anonymized queries, so rows add up to less than the summary totals. Requires a connected Search Console property (Growth+) and live reads: stored reads return ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access and ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. A combination Google refuses comes back as ERR_INVALID_PARAM with its reason.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**dimensions** | **String** | Comma-separated dimensions to group by, 1 to 3 of date, country, device, page, query, searchAppearance. Each becomes a field of every row; country and device values are lowercase. | [required] |
**range** | Option<**u32**> | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention. |  |
**from** | Option<**chrono::NaiveDate**> | Start date (YYYY-MM-DD). Defaults to 30 days ago. |  |
**to** | Option<**chrono::NaiveDate**> | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. |  |
**sort** | Option<**String**> |  |  |[default to impressions]
**page** | Option<**u32**> |  |  |[default to 1]
**per_page** | Option<**u32**> |  |  |[default to 20]
**start_row** | Option<**u32**> | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. |  |[default to 0]
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |
**search_type** | Option<**String**> | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. |  |[default to web]
**filters** | Option<**String**> | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. |  |
**data_state** | Option<**String**> | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. |  |[default to final]
**aggregation_type** | Option<**String**> | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. |  |[default to auto]

### Return type

[**models::SearchConsoleRowsResponse**](SearchConsoleRowsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_search_console_summary

> models::SearchConsoleSummaryResponse get_search_console_summary(project_id, range, from, to, dimension, limit, search_type, filters, data_state, aggregation_type)
Search Console summary (Growth+)

Google Search Console headline totals (impressions, clicks, ctr as a 0..1 fraction, average position) for the project over a date range. Pass dimension=country, device, page, query or searchAppearance to also receive the breakdown aggregated over the range, capped by limit. With filters and no dimension, totals are the complete figure Google reports for that filter. Breakdown rows are capped by limit and by Google's 25,000-row maximum; breakdown_truncated: true means rows were left out. Query rows exclude anonymized queries, and page and searchAppearance rows are counted per page rather than per property, so breakdown rows can differ from the totals. Requires the project to have a connected Search Console property and the Growth plan or above; otherwise returns ERR_SEARCH_CONSOLE_NOT_CONNECTED or ERR_PLAN_REQUIRED. X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**u32**> | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention. |  |
**from** | Option<**chrono::NaiveDate**> | Start date (YYYY-MM-DD). Defaults to 30 days ago. |  |
**to** | Option<**chrono::NaiveDate**> | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. |  |
**dimension** | Option<**String**> | Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive. |  |
**limit** | Option<**u32**> | Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through up to 25,000 rows. |  |
**search_type** | Option<**String**> | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. |  |[default to web]
**filters** | Option<**String**> | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. |  |
**data_state** | Option<**String**> | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. |  |[default to final]
**aggregation_type** | Option<**String**> | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. |  |[default to auto]

### Return type

[**models::SearchConsoleSummaryResponse**](SearchConsoleSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_search_console_timeseries

> models::SearchConsoleTimeseriesResponse get_search_console_timeseries(project_id, range, from, to, granularity, output, search_type, filters, data_state, aggregation_type)
Search Console time series (Growth+)

Google Search Console series (impressions, clicks, ctr, position) bucketed by day, week or month, property-wide unless filters narrows it. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**project_id** | **i32** | Project ID | [required] |
**range** | Option<**u32**> | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention. |  |
**from** | Option<**chrono::NaiveDate**> | Start date (YYYY-MM-DD). Defaults to 30 days ago. |  |
**to** | Option<**chrono::NaiveDate**> | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. |  |
**granularity** | Option<**String**> |  |  |
**output** | Option<**String**> | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON. |  |
**search_type** | Option<**String**> | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. |  |[default to web]
**filters** | Option<**String**> | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. |  |
**data_state** | Option<**String**> | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. |  |[default to final]
**aggregation_type** | Option<**String**> | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. |  |[default to auto]

### Return type

[**models::SearchConsoleTimeseriesResponse**](SearchConsoleTimeseriesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

