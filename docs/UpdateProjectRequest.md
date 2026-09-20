# UpdateProjectRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**brand_name** | Option<**String**> | Brand name used to detect mentions. Applies to future runs; it does not rewrite history | [optional]
**description** | Option<**String**> | What the brand does. Context for Recommendations and GEO Writer (Brand Book) | [optional]
**industry** | Option<**String**> | Single industry key (e.g. SAAS); unknown keys are rejected | [optional]
**business_model** | Option<**String**> | Business model key (e.g. B2B_SAAS); unknown keys are rejected | [optional]
**business_model_other** | Option<**String**> | Free-text business model, only accepted when business_model is OTHER; rejected against any other key | [optional]
**target_audience** | Option<**String**> | Who the brand sells to (Brand Book) | [optional]
**brand_voice** | Option<**String**> | Tone of voice guidance for generated content (Brand Book) | [optional]
**goals** | Option<**String**> | What the brand wants to achieve. Context for GEO Writer and prompt suggestions | [optional]
**primary_products** | Option<**Vec<String>**> | Full replacement list of the main products or services | [optional]
**matching_names** | Option<**Vec<String>**> | FULL replacement list of the brand-name variants used to detect mentions; send every variant to keep | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


