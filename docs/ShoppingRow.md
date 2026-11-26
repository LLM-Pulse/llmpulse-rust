# ShoppingRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**product_key** | Option<**String**> | Stable grouping key of the product: its external id, else title: and the lowercased title (view=products) | [optional]
**title** | Option<**String**> |  | [optional]
**domain** | Option<**String**> |  | [optional]
**url** | Option<**String**> |  | [optional]
**merchants** | Option<**String**> | The merchants the product card names (view=products) | [optional]
**merchant** | Option<**String**> | The merchant (view=merchants) | [optional]
**products** | Option<**i32**> | Distinct products the merchant sold (view=merchants) | [optional]
**currency** | Option<**String**> | Currency code the prices are in; null when no price names one | 
**currency_count** | Option<**i32**> | Currencies the product was priced in; above 1 the row reports its highest-priced listing (view=products) | [optional]
**min_price** | Option<**f64**> |  | 
**max_price** | Option<**f64**> |  | 
**avg_price** | Option<**f64**> | Average price in currency (view=merchants) | [optional]
**avg_rating** | Option<**f64**> |  | 
**rating_votes** | Option<**i32**> | Most rating votes any listing of the product showed (view=products) | [optional]
**appearances** | **i32** |  | 
**is_client** | Option<**bool**> | Whether the product is identified as your brand's own (view=products) | [optional]
**best_rank** | Option<**i32**> | Best rank the product got in a card list (view=products) | [optional]
**models** | Option<**Vec<Models>**> | Models that showed the product (view=products) (enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode, bing_ai_overview) | [optional]
**last_seen_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | The latest answer that showed the product (view=products) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


