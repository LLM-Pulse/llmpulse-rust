# OwnedMediaSummaryActivityPeriod

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | **chrono::NaiveDate** | Start date of the actual reporting period | 
**citations** | **i32** |  | 
**yours** | Option<**i32**> | Citations on owned profiles and content, null for provider=overview | 
**other** | Option<**i32**> | Citations not counted as yours, null for provider=overview | 
**positive** | Option<**i32**> | Citations whose AI answer sentiment is positive | [optional]
**neutral** | Option<**i32**> | Citations whose AI answer sentiment is neutral or mixed | [optional]
**negative** | Option<**i32**> | Citations whose AI answer sentiment is negative | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


