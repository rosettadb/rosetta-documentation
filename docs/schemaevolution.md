In Rosetta, the Schema Evolution category empowers users to track and visualize changes made to catalogs over time. This feature provides a clear view of data lineage, allowing users to observe alterations made to columns and schemas.

When users select a specific date, any changes made to the catalog since that time are displayed. For enhanced clarity, modified columns are highlighted in orange, while deleted columns are highlighted in red. This intuitive color-coded system enables users to quickly identify and understand the evolution of their data schemas.

This functionality is invaluable for maintaining data integrity and ensuring transparency in data management processes.
## Example

To view the catalog changes over time, the user must click on `Schema Evolution` category tab and choose a catalog that wants to view the data lineage.

![](../images/schemaEvolution/schemaEvolution.png)

When the user clicks on the catalog, a new graphical view of all the runs is shown. The graph points represent the data lineage in time when that catalog was run.

![](../images/schemaEvolution/graphicalRepresentation.png)

![](../images/schemaEvolution/schemaRun.png)

With this feature, the user is able to compare the catalog changes during specific times.

For example, in the picture below, during the first run, Generation 1 there were 30 fields and in the second run there are only 22 fields, where 8 fields are deleted and are colored with red.

![](../images/schemaEvolution/schemaDelete.png)

If the user hovers on the point of change in the graph there will be a detailed view of what was changed during the runs.

![](../images/schemaEvolution/schemaDeleteDetails.png)

Now if the user goes to the Catalogs, adds some fields, and runs the catalog, it can see the new run in the data lineage, Generation 2. From two runs that were in the previous example, now there are three v1, v2, and v3.

The new columns that are added are colored with green and the number of fields from 22 became 23.

![](../images/schemaEvolution/schemaAdd.png)

![](../images/schemaEvolution/schemaAddDetails.png)

Lastly, if the user wants to make a change in the current schema, add a tag or remove one, it needs to return back to Catalogs, make the changes and run the catalog again. From three runs that were in the previous example, now there will be four.

The columns that are modified are colored orange and the user can see the tag and label icon on the columns.

![](../images/schemaEvolution/schemaModify.png)

![](../images/schemaEvolution/schemaModifyDetails.png)

All these changes in one are captured in the picture below.
Column `actor` is modified and colored with orange, column `payment` is deleted, has removed the label and colored with red, and column `actor_salary` is added to the schema and colored with green.

![](../images/schemaEvolution/schemaAll.png)

To view more details the user can expand the list of changes and can see them described.

![](../images/schemaEvolution/schemaAllDetails.png)
