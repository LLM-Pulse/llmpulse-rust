# QueryFanOutsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**page** | **i32** |  | 
**per_page** | **i32** |  | 
**total** | **i32** | Rows matching the filters across every page | 
**request_id** | **String** |  | 
**view** | **String** | query or prompt, the row shape of data | 
**total_occurrences** | Option<**i32**> | Sub-query occurrences across every page (view=query) | [optional]
**data** | [**Vec<models::QueryFanOutRow>**](QueryFanOutRow.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


