# CitedUrlDetailsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**url_sha256** | **String** |  | 
**url** | Option<**String**> | The URL as first cited | 
**normalized_url** | **String** |  | 
**domain** | Option<**String**> |  | 
**host** | Option<**String**> |  | 
**stats** | [**models::CitedUrlDetailsResponseStats**](CitedUrlDetailsResponseStats.md) |  | 
**urls** | **Vec<String>** | Up to 20 spellings of the URL as cited, alphabetically | 
**page_details** | [**models::CitationPageDetails**](CitationPageDetails.md) |  | 
**citation_series** | Option<[**models::CitationSeries**](CitationSeries.md)> |  | [optional]
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


