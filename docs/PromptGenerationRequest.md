# PromptGenerationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **i32** |  | 
**source** | **Source** | Which Add prompts generator to run (enum: website, keyword, topic, reddit, paa, reputational, translate, search_console) | 
**query** | Option<**String**> | keyword: optional keyword or research query. topic and reddit: required topic (reddit: the brand when search_type=brand). paa: one keyword, as an alternative to keywords. | [optional]
**count** | Option<**u32**> | keyword and topic: how many suggestions to ask for, capped by the prompt slots left | [optional][default to 20]
**country_code** | Option<**String**> | ISO 3166-1 alpha-2 country of the suggestions (default the project country) | [optional]
**language_code** | Option<**String**> | ISO language code of the suggestions (default the project language) | [optional]
**competitor_id** | Option<**i32**> | keyword: write the suggestions around this competitor of the project | [optional]
**search_type** | Option<**SearchType**> | reddit: search discussions of a topic or a brand (enum: topic, brand) | [optional][default to Topic]
**keywords** | Option<**Vec<String>**> | paa: up to 5 keywords; each is a People Also Ask lookup counted against the account's 24-hour allowance | [optional]
**source_country_code** | Option<**String**> | translate: country of the prompts to translate | [optional]
**source_language_code** | Option<**String**> | translate: language of the prompts to translate | [optional]
**min_words** | Option<**u32**> | search_console: skip queries shorter than this many words | [optional][default to 0]
**all_countries** | Option<**bool**> | search_console: include queries from every country instead of country_code only | [optional][default to false]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


