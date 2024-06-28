Data Sources category is where users establish and create connections to various data sources. Users have the flexibility to choose from fifteen options, including JDBC drivers, files, FTP, Google Cloud Storage (GCS), Amazon Simple Storage Service (Amazon S3), Microsoft Azure, HDFS, DB2, Oracle, Snowflake, BigQuery, MsSQL, PostgreSQL, MySQL, and Kinetica.

Supported database servers encompass MySQL, MS SQL Server, Postgres, Oracle, BigQuery, and Generic drivers. To set up a new data source connection, users input details such as the connection name, description, server host and port, database name, username, and password. Additionally, users define a driver class name, upload a JDBC driver if necessary, provide a token, and more.

Once all necessary fields are filled, the information is saved, and the newly created data source connection is displayed in a list format within the Data Source Connections section. Users can then manage these connections with options to edit or delete them.

## Example

### Create a data source

To create a data source, the user must click on the Data Source tab from the menu on the left.

If there are no data sources configured, the user clicks on `Add Data Source` button to add a new data source.

![](../images/datasources/addDataSourceDashboard.png)

When `Add Data Source` button is clicked, a new screen with fifteen options to choose from for data source connection is shown.

![](../images/datasources/datasourceTypes.png)

![](../images/datasources/datasourceTypes2.png)

#### JDBC connection

If the user chooses JDBC connection type, must fill in some fields such as a connection name that should be unique, a description, hostname, and port based on the DB server chosen from the dropdown list, and configured username and password for the data source, the JDBC driver should be uploaded and JDBC connection string should be given in a format <code>jdbc:sqlserver://{host}[:{port}][databasename={database}]</code>.

When the user fills all the fields the connection can be tested by clicking the button `Test` which will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/datasourcefilled.png)

#### File connection

If the user chooses file connection type the user needs to fill in a name, choose a type of the file, CSV, Avro, or parquet, and fill in the URI of the file.

When the user fills all the fields the connection can be tested by clicking the button `Test` which will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/fileconnection.png)

#### FTP connection

If the user chooses FTP connection type it needs to fill in a name, choose a type, a directory, CSV, Avro or parquet, and fill in the URI of the file starting with `file://`. In order to explore what files are inside the directory by clicking on `Explore` the user must specify the URI. If it clicks on one of the files of that directory, the URI will be rewritten automatically.

After clicking `Save` button all the input is saved and the data source is ready for use.
![](../images/datasources/ftpdatasourceexplore.png)

![](../images/datasources/ftpdatasource.png)

#### Google Bucket connection

If the user chooses Google Bucket connection type the user needs to fill in a name, choose a type, a directory, CSV, Avro, or parquet, write the service account key, and fill in the URI of the file starting with `gs://`. The user can explore what files are inside the bucket by clicking on `Explore`, even without filling the URI . If it clicks on one of the files or directories of that bucket, the URI will be filled or rewritten automatically.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/gcsconnectionexplore.png)

![](../images/datasources/gcsconnection.png)

#### S3 Amazon connection

If the user chooses S3 Amazon connection type the user needs to fill in a name, choose a schema type of the file, CSV, Avro, or parquet, provide access key ID and secret access key, and fill in the URI of the file starting with `s3a://`. The user can explore what files are inside the bucket by clicking on `Explore`, even without filling in the URI. If it clicks on one of the files or directories of that bucket, the URI will be filled or rewritten automatically.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/s3connectionexplore.png)

<!-- ![](../images/datasources/s3connection.png) -->

#### Microsoft Azure connection

If the user chooses Microsoft Azure connection type the user needs to fill in a name, choose a schema type of the file, CSV, Avro, or parquet, provide the Account name, Container name, and SAS token, and fill in the URI of the file starting with `wasbs://`. The user can explore what files are inside the bucket by clicking on `Explore`, even without filling in the URI. If it clicks on one of the files or directories of that bucket, the URI will be filled or rewritten automatically.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/azureconnection.png)

#### HDFS connection

If the user chooses HDFS connection type it needs to fill in a name, choose a type, a directory, CSV, Avro, or parquet, and fill in the URI of the file starting with `file://`. In order to explore what files are inside the directory by clicking on `Explore` the user must specify the URI. If it clicks on one of the files in that directory, the URI will be reswritten automatically.

When the user fills all the fields the connection can be tested by clicking the button `Test` that will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/hdfsconnectionexplore.png)

![](../images/datasources/hdfsconnection.png)

#### DB2 connection

If the user chooses DB2 connection type, must fill in some fields such as a connection name that should be unique, a description, hostname, and port, configured username and password for the data source, the driver should be uploaded and the JDBC connection string should be given in a format <code>jdbc:db2://${host}:${port}</code>.

When the user fills all the fields the connection can be tested by clicking the button `Test` that will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/db2filled.png)

#### Oracle connection

If the user chooses Oracle connection type, must fill in some fields such as a connection name that should be unique, a description, hostname, and port, configured username and password for the data source, the driver should be uploaded and JDBC connection string should be given in a format <code>jdbc:oracle:thin:@//${host}:${port}</code>.

When the user fills in all the fields the connection can be tested by clicking the button `Test` which will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/oraclefilled.png)

#### Snowflake connection

If the user chooses Snowflake connection type, must fill in some fields such as the connection name that should be unique, a description, hostname, and port, configured username and password for the data source, the driver should be uploaded and JDBC connection string should be given in a format  <code>jdbc:snowflake://${host}:${port}/db=dbname</code>.

When the user fills all the fields the connection can be tested by clicking the button `Test` which will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/snowflakefilled.png)

#### BigQuery connection

If the user chooses the BigQuery connection type, must fill in some fields such as the connection name that should be unique, a description, the database name, the driver that should be uploaded and the JDBC connection string should be given in a format  <code>jdbc:bigquery://{host}[:{port}][;databaseName={database}]</code>.

When the user fills all the fields the connection can be tested by clicking the button `Test` that will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/bigqueryfilled.png)

#### Microsoft SQL Server connection

If the user chooses Microsoft SQL Server connection type, must fill in some fields such as a connection name that should be unique, a description, hostname, and port, configured username and password for the data source, the driver should be uploaded and the connection string should be given in a format <code>jdbc:sqlserver://{host}[:{port}][databasename={database}]</code>.

When the user fills in all the fields the connection can be tested by clicking the button `Test` which will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/msqlfilled.png)

#### PostgreSQL connection

If the user chooses PostgreSQL connection type, must fill in some fields such as the connection name that should be unique, a description, hostname, and port, configured username and password for the data source, the driver should be uploaded and the connection string should be given in a format <code>jdbc:postgresql://${host}:${port}</code>.

When the user fills all the fields the connection can be tested by clicking the button `Test` which will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/postgresqlfilled.png)

#### MySQL connection

If the user chooses MySQL connection type, must fill in some fields such as a connection name that should be unique, a description, hostname, and port, configured username and password for the data source, the driver should be uploaded and the connection string should be given in a format <code>jdbc:mysql://${host}:${port}</code>.

When the user fills all the fields the connection can be tested by clicking the button `Test` that will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/mysqlfilled.png)

#### Kinetica connection

If the user chooses Kinetica connection type, must fill in some fields such as a connection name that should be unique, a description, hostname and port, a database name, configured username and password for the data source, attributes such as key-value pairs that can be added, the driver should be uploaded and connection string should be given in a format <code>jdbc:kinetica:URL=http://${host}:${port}</code>.

When the user fills in all the fields the connection can be tested by clicking the button `Test` which will turn green if the connection is correct, and turn red if the connection is wrong.

After clicking `Save` button all the input is saved and the data source is ready for use.

![](../images/datasources/kineticafilled.png)

### Edit a data source

Now that one data source is configured, on the Data Source tab the user can see a list of the data sources and a button `Add Data Source` that redirects to the Data source screen for creating a new data source. The data source can be edited, deleted and searched.

![](../images/datasources/datasourcelist.png)

When the user clicks on the pen icon next to the data sources from the list they can edit some of the fields and save the changes.

![](../images/datasources/editdatasource.png)

### Delete a data source

The deletion of a data source is done by clicking on the bin icon.

![](../images/datasources/deletedatasource.png)

When the icon is clicked, a pop-up appears with a question if the user is sure about deleting the data source, and if yes the user clicks Delete and if not clicks Cancel.

![](../images/datasources/deletedatasourcequestion.png)

### Search for a data source

The user can search for a data source from the list of data sources. The data source that we created as an example is named `data source demo`, so if the user searches for `test` there will be no results.

![](../images/datasources/searchdatasource.png)
