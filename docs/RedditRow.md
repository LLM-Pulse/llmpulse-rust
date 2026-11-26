# RedditRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**subreddit** | Option<**String**> | Subreddit name without the r/ prefix; null on a thread whose subreddit is unknown | [optional]
**author** | Option<**String**> | Reddit username; null on a thread whose author is unknown | [optional]
**url** | Option<**String**> | The subreddit, author profile or thread URL | [optional]
**title** | Option<**String**> | Thread title, read from the post or its URL (view=threads) | [optional]
**citations** | Option<**i32**> | Reddit citations of the row in the window | [optional]
**unique_authors** | Option<**i32**> | Distinct authors cited in the subreddit (view=subreddits) | [optional]
**positive** | Option<**i32**> | Citations in answers with a positive or very positive sentiment | [optional]
**negative** | Option<**i32**> | Citations in answers with a negative or very negative sentiment | [optional]
**neutral** | Option<**i32**> | Citations in answers with a neutral sentiment | [optional]
**positive_pct** | Option<**f64**> | positive over the rated citations, 0-100; null when none is rated (view=subreddits) | [optional]
**negative_pct** | Option<**f64**> | negative over the rated citations, 0-100; null when none is rated (view=subreddits) | [optional]
**yours** | Option<**bool**> | Whether the account claims the subreddit or author as its own (on threads, either of them) | [optional]
**subreddits** | Option<**Vec<String>**> | The first subreddits the author was cited in (view=authors) | [optional]
**extra_subreddits** | Option<**i32**> | Further subreddits the author was cited in, beyond those listed (view=authors) | [optional]
**leaning** | Option<**String**> | positive, negative or neutral, whichever sentiment has more of the author's citations (view=authors) | [optional]
**brands** | Option<[**Vec<models::RedditAuthorBrand>**](RedditAuthorBrand.md)> | Brands the content of the author's cited posts names, your own first (view=authors) | [optional]
**subreddit_yours** | Option<**bool**> | Whether the account claims the thread's subreddit (view=threads) | [optional]
**author_yours** | Option<**bool**> | Whether the account claims the thread's author (view=threads) | [optional]
**latest_cited_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | The thread's most recent citation (view=threads) | [optional]
**upvotes** | Option<**serde_json::Value**> | Upvotes as the scraped post reports them, a number or a numeric string, or null when unknown (view=threads) | [optional]
**comments** | Option<**serde_json::Value**> | Comment count as the scraped post reports it, a number or a numeric string, or null when unknown (view=threads) | [optional]
**avg_position** | Option<**f64**> | Average rank of the thread's citations, 1 = first; null when no citation has a visible rank (view=threads) | [optional]
**sentiment** | Option<**String**> | The most frequent sentiment of the answers that cite the thread; null when none is rated (view=threads) | [optional]
**archived** | Option<**serde_json::Value**> | Whether the thread is archived as the scraped post reports it, usually a boolean, or null when unknown (view=threads) | [optional]
**posted_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the thread was posted; null when unknown (view=threads) | [optional]
**breakdown** | Option<**String**> | sentiment, model or country (view=breakdowns) | [optional]
**key** | Option<**String**> | The slice, a sentiment label, a model or an uppercase country code (view=breakdowns) | [optional]
**count** | Option<**i32**> | Reddit citations in the slice (view=breakdowns) | [optional]
**pct** | Option<**f64**> | Share of the slice within its breakdown, 0-100 (view=breakdowns) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


