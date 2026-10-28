# CreateApiKeyRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **String** | A label to recognize the key, for example the customer it is for | 
**scope** | Option<**Scope**> | read (default) only reads data; read_write can also create, change and delete within the key's projects (enum: read, read_write) | [optional][default to Read]
**project_ids** | **Vec<i32>** | The projects the key is limited to, at least one | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


