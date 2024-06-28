Alerts category allows users to set up alerts for their catalogs. Setting up alerts in Adaptive Scale is straightforward by filling some general info such as name, description, then choose a catalog, an input rule and out rule.

## Example

### Create an alert

To create an alert, the user simply needs to click on the `Alerts` tab from the menu on the left. 

If there are no alerts configured, the user clicks on `New Alert` button to add a new alert.

![](../images/alerts/addAlert.png)

After the button is clicked, the `Alerts` screen is opened. The user must fill the general information such as Alerts name, description and choose the catalog for which it needs to create the alert. 
The next step is to choose an input rule between `Size in bytes`, `Total records` and `SQL checks`, and then choose an execution rule between `Run SQL`, `API Call` and `Send Email`.

![](../images/alerts/alertscreen.png)

#### Input rules

`Size in bytes` - allows users to choose a table from the selected catalog and check a value with an operator.

![](../images/alerts/sizeInBytes.png)

`Total records` - allows users to choose a table from the selected catalog and check the total records by choosing an operator and give a value for that table.

![](../images/alerts/totalRecords.png)

`SQL Check` - The SQL input rule will be fulfilled if the query returns any row.

![](../images/alerts/sqlCheck.png)

#### Execution rules
If the input rule is fulfilled then the execution rule gets executed.

`Run SQL` - on the dropdown choose a data source, and the SQL query will be executed on that data source.

![](../images/alerts/runSql.png)

`Api Call` - the user is able to make a GET and a POST api call, by giving the uri, and fill the header, value and the body if needed.

![](../images/alerts/apiCall.png)

`Send Email` - this allows users to send an email.

![](../images/alerts/sendEmail.png)

After clicking `Save` button all the configurations are saved and the alert is ready.


### Edit an alert

Now that an alert is configured, on Alerts tab the user can see a list of the alerts and a button `Add Alert` that redirects to the Alerts screen for creating a new one. The alert can be edited, deleted, activated/deactivated and searched.

![](../images/alerts/alertsList.png)

When the user clicks on the pen icon next to the alert from the list they can edit the name, description, the catalog for the alert, also change the input and execution rules.

![](../images/alerts/editalert.png)

### Delete an alert

The deletion of an alert is done by clicking on the bin icon.

![](../images/alerts/deletealert.png)

When the icon is clicked, a popup appears with a question if the user is sure about deleting the collection, and if yes the user clicks Delete and if not clicks Cancel.

![](../images/alerts/deletealertquesstion.png)

### Search for an alert

The user can search for an alert from the list of alerts. The alert that we created as an example is named `Alert Demo`, so if the user searches for `test` there will be no results.

![](../images/alerts/searchalert.png)

### Activate/Deactivate alert

When the user creates an alert, by default it is set in `Active` alerts list. This means that the next run of the catalog will trigger the alert, and it will be visible at the bell icon on the top.

![](../images/alerts/notification.png)

![](../images/alerts/alertNotification.png)

If the user clicks on the alert is able to see the alerts detailed report, the history and status of the run.

![](../images/alerts/alertReport.png)

All this happens if the toggle is on Active, if the toggle is set to Deactivate than the user won't get an alert when it runs the catalog. The grey color indicates that the alert is deactivated.

![](../images/alerts/deactiveAlert.png)