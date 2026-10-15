# CustomReportWidget

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | **String** |  | 
**label** | **String** |  | 
**kind** | **Kind** |  (enum: kpi_grid, timeseries, donut, bar, table) | 
**width** | **Width** |  (enum: half, full) | 
**available** | **bool** | false when the widget's data source (web analytics, agent analytics, owned media) is not connected | 
**data** | Option<**std::collections::HashMap<String, serde_json::Value>**> | Shaped by kind. timeseries: series [{ name, color, points [{ date, value }] }]. donut: slices [{ name, value, color }]. bar: bars [{ label, value, color }]. kpi_grid: values and changes (null unless the report compares with the previous period). table: rows, one object per row. Null when the widget is not available. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


