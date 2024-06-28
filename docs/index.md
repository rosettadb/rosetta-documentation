<p align="center">
  <a href="http://127.0.0.1:8000/"><img src=" ../images/rosetta.png" alt="AdaptiveScale"></a>
</p>
<p align="center">
    <em>Data Management, powered by Metadata!</em>
</p>

---


Data is a key asset for enterprises, yet finding the right data on the right systems can be elusive. Rosetta  allows you to leverage the metadata from your data sources to discover and organize data. Rosetta  helps catalog all the data sources and files that a user wants to discover and centralizes that metadata in a single location. Catalog generation with tagging and labeling is supported down to the column level, and the scheduling is customizable for catalog triggers. Scheduling is an important part of the cataloging process because as data is mutated in respective data sources something needs to keep track of what changes are taking place and captures that lineage. All your metadata is searchable and it's powered by ElasticSearch. Users can also query and browse any JDBC-compliant database in SQL Explorer. You can also use your catalog as a curated source for transferring the data, with associated filtering and governance policies applied to cloud storage or Hadoop HDFS. Cloud storage support includes Amazon S3, Azure Data Lake Storage, and Google Cloud Storage.

## Categories

The dashboard provides general statistics for how many data sources the user has crawled, how many catalogs have been created, and how many tags or labels are created. The Rosetta  JDBC driver, which you can download directly from the dashboard, allows you to connect to Rosetta  using your favorite JDBC-compliant development environment to browse and query cataloged data sources with SQL. To help the users get more familiar with Rosetta, there are links to User Guides, Tutorials, and Documentation. The user interface is organized into the following categories: Data Sources, Catalogs, Tags, Schedules, Schema Evolution, Search, SQL Explorer, Data Transfer, and Collections.

### <a href="../datasources/"> Data sources </a>

Data Sources is the category where the user defines a data source connection. There are six options to choose from; a JDBC driver, file, file transfer protocol(FTP), Google Bucket, Amazon S3, and Microsoft Azure. The supported database servers are MySQL, MS SQL Server, Postgres, Oracle, BigQuery, and Generic driver. The Generic driver expands the database list to any JDBC-compliant database so you can connect to any database that provides a JDBC driver. To create a new data source connection fill in the connection name, description, host and port for the server, database name for the utilized database server with a username and password, define a driver class name, and upload a JDBC driver. All these fields are saved and the newly created data source connection is shown in a list of Data Source connections. Once saved the connection will be displayed in a list where you have the option to edit or delete it. For a new file or FTP data source connection fill in the connection name, choose the URI of the file, and from the dropdown choose CSV or AVRO, which should be the same as the type of the file. The same applies to the other connections that are left with some small differences, for example, for the Google Bucket data source connection you must add the Service Account, for Amazon S3 you must provide the Access Key ID and Secret Access Key and for Microsoft Azure, you should provide Account Name, Container Name, and SAS Token.

### <a href="../catalogs/"> Catalogs </a>

Catalogs is where you create the catalog based on the metadata of the data source. In catalog generation, tagging and labeling are supported. To create a new catalog the user needs to fill in the catalog name, which needs to be a unique name to prevent any kind of naming collisions, choose a data source from existing ones or the newly created one from where all the columns and tables are going to be retrieved. In the Details section, you have the option to fetch the total counts of records within the data source. Record counts are fetched every time a scheduled catalog is triggered and will automatically be included in the catalog metadata. There are two important features inside the catalog category, one is for tagging and labeling, and the other is for scheduling, where you can select a time interval for when the catalog crawler should be run. All these changes are saved and the new catalog is shown in a list of catalogs with fields that have all the statistics calculated and set in the previous step, including how many tables and columns were crawled, when it was last run, next run, and options to edit, delete and run the catalog. With the run option, the crawler retrieves all the information from the data source and it applies the catalog rules set.

### <a href="../tags/"> Business Rules </a>

Business Rules allow you to automatically tag tables and columns with pattern matching. To create a business tag, the user needs to provide a tag name, description, and optionally a collection name. In the tags section, you can also apply matching patterns to tag more than one column with the same characteristics and also apply Business Rules for data governance by masking and filtering data using JavaScript code blocks. You can also define your tags externally and import them as a CSV file.

### <a href="../schedules/"> Schedules </a>

Schedules list all active and inactive crawlers defined for catalogs, with information like the catalog name, last run, next scheduled run, options to activate or deactivate a schedule, and the option to delete it.

### <a href="../schemaevolution/"> Schema evolution </a>

Schema evolution allows you to choose a catalog and see the changes that have been made to that catalog over time. The lineage can be seen very clearly; for example when the user selects a date, the column or table that has been changed is highlighted with highlight colors.

### <a href="../search/"> Search </a>

Search screen allows you to search by tags, field names, table names, data source names, and more. Here’s a list of supported filters: string, wild card:

- `*(string)*`
- `tag: <tag name (string)>`
- `key: <key name (string)>`
- `val: <(string)>`
- `table: <table name>`
- `column: <field name>`
- `data source: <data source name>`

If for example, you searche for a tag name, it retrieves that tag with how many matches it finds. The user can also see the data lineage from the search section when clicking on the column.

To understand more about it, see the sections on the right.

### <a href="../sqlexplorer/"> SQL Explorer </a>

SQL Explorer allows you to choose a JDBC data source connection, view the schema, and query or browse any JDBC-compliant database in the SQL.

### <a href="../datatransfer/"> Data Transfer </a>

Data Transfer is used for exporting data from a selected catalog to cloud storage and HDFS, including Google Cloud Storage, Amazon S3, and Azure Data Lake Storage.
