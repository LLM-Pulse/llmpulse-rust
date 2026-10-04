# IntelligenceTaskCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**task_type** | **TaskType** | product_listing is API-only: it needs product and returns ready-to-apply product page copy (enum: brief, create, update, pr_insights, custom, product_listing) | 
**prompt_id** | Option<**i32**> | Not used by product_listing; send null or omit it | [optional]
**custom_topic** | Option<**String**> |  | [optional]
**user_instructions** | Option<**String**> |  | [optional]
**output_language_code** | Option<**String**> |  | [optional]
**existing_content** | Option<**String**> |  | [optional]
**existing_content_url** | Option<**String**> |  | [optional]
**product** | Option<[**models::IntelligenceTaskProduct**](IntelligenceTaskProduct.md)> |  | [optional]
**prompt_ids** | Option<**Vec<i32>**> | product_listing only: up to 20 project prompts the copy should answer | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


