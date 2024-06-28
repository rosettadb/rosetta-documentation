SQL Explorer is the category designed to assist users in extracting information from various data sources.

The interface presents users with a dropdown menu to select the data source they wish to query and a SQL Explorer editor where users can input structured query language-formatted queries.

![](../images/sqlexplorer/firstScreenSqlExplorer.png)

Key features include:

- A "Run Query" button that executes the query entered in the editor.
- A "Limit" dropdown menu that specifies the maximum number of results to display, with options including 10, 100, and 1000.

When users select a data source from the dropdown menu, all tables and columns associated with that data source are displayed in a tree view on the left side of the screen. This visual representation facilitates users in inspecting the contents of their data source and simplifies the process of querying information.

![](../images/sqlexplorer/catalogOverview.png)

## Example

Since no query has been executed yet, no results are displayed. Let's demonstrate by running some queries to observe the results table.

For this example, let's retrieve all the `actors` from the data source. Following the standard SQL syntax, we start with the "SELECT" command to specify the fields we want to retrieve. The "FROM" command indicates the source from which to extract data. Upon clicking the `Run Query` button, the result table will be generated.

![](../images/sqlexplorer/queryResult.png)

Below the SQL editor, the results table is populated with data retrieved from the executed query. The table may contain multiple records, which are displayed across pages based on the selected limit from the dropdown menu.

This functionality streamlines the process of querying data, enabling users to extract valuable insights from their data sources effectively.
