# ProjectUpdateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project** | [**models::ProjectProfile**](ProjectProfile.md) |  | 
**updated_fields** | **Vec<String>** | The fields the request sent | 
**rematching** | **bool** | True when a matching_names or additional_owned_domains change started a background recalculation of past answers; further edits are rejected until it finishes | 
**note** | **String** | What the change does to mention detection, citation ownership, historical numbers and the prompts the project can hold | 
**request_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


