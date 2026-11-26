# AnalystScoreRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**brand** | **String** | Brand name; the subject name in a custom study | 
**is_project** | **bool** | Whether it is the project's own brand; in a custom study, the focus subject | 
**model** | **Model** |  (enum: chatgpt, perplexity, gemini, deepseek, grok, claude) | 
**report_date** | **chrono::NaiveDate** |  | 
**dimension** | **String** | Dimension key, as the dimension filter takes it | 
**dimension_name** | **String** |  | 
**attribute** | **String** | Attribute key within the dimension | 
**attribute_name** | **String** |  | 
**score** | Option<**serde_json::Value**> | The 0-100 score as the analyst model wrote it, normally a number, or null when it gave none. Deliberately untyped, as the model's output is stored without coercion | 
**reasoning** | Option<**String**> | Why the model gave this score; null when it gave no reasoning | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


