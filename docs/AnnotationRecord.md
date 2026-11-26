# AnnotationRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**title** | **String** |  | 
**description** | Option<**String**> |  | 
**annotation_date** | **chrono::NaiveDate** |  | 
**color** | Option<**String**> |  | 
**category** | **String** | user (written by a person) or system (added by the platform) | 
**origin** | **String** | manual, platform (a platform-wide event) or automation (a project change recorded automatically) | 
**annotation_category** | Option<[**models::AnnotationRecordAnnotationCategory**](AnnotationRecordAnnotationCategory.md)> |  | 
**editable** | **bool** | Whether the requesting user may update or delete it | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


