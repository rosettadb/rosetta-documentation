Search category provides users with a powerful tool for searching and retrieving data based on various criteria such as tags, field names, table names, and data source names. Users can utilize a range of supported filters including string and wildcard searches.

Supported filters include:

- `*(string)*`
- `wild card: *(string)*`
- `tag: <tag name (string)>`
- `key: <key name (string)>`
- `val: <(string)>`

For example, if a user searches for a specific tag name, Rosetta  queries the ElasticSearch database to retrieve matches and provides the user with the results. Additionally, users can explore data lineage directly from the search section by clicking on specific columns.

## Example

In the Metadata Search tab, users can search by tags, field names, table names, data source names, and more.

![](../images/search/metadataSearch.png)

Let's perform a search for each of these criteria.

From earlier examples, we can recall that we tagged a column with a tag named `pii`, so if we search for `pii`, we will have a result.

![](../images/search/tagSearched.png)

Now that the user has searched for `pii`, the results are displayed in a list format, accompanied by a dashboard showing statistics such as the number of data sources, records, fields, tags, and labels crawled from that search.

![](../images/search/tagSearchResult.png)

This functionality allows users to efficiently explore and analyze data within Rosetta , enabling informed decision-making and data-driven insights.