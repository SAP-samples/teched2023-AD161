# Exercise 4 - Add Sample Data

We will now populate our data model with some sample data so that we can test our service. Note, that even though it says sample data, the data can be of two types:
- Fixed values that are part of your application and should be deployed along with the application. An example could be the data for **Urgency** if there is only a fixed set of urgencies that cannot be changed
- Sample data that is only used to test the services and applications that you create and that should not be part of a productive deployment.

Go to the **Storyboard** and from the **Data Models** tile, click the **Urgency** entity and select **Add Sample Data**.
The Sample Data Editor opens.

From the editor, select **Urgency**.
Change the **Mock Data** switch to **Off** and enter 3 as the number of rows.
Click **Add**:
In the descr field, enter Low, Medium and High accordingly.

![](/exercises/Ex4/images/urgencysampledata.png)  

Now we will **import** data from a file to **A_BusinessPartner** entity.

Open the Customers file 
![Customers](/exercises/Ex4/csv/customers.csv)  
and press download.

Alternatively, Using a local text editor, create a local file named `customers.csv`.
Add the following content to the file and save it locally:
```
BusinessPartner,FirstName,LastName
1001036,Daniel,Watts
1001038,Stormy,Weathers
1001039,Sunny,Sunshine
```

From the editor, select **A_BusinessPartner** and click **Import**.
From the file selection dialog box that opens, select the 'customers.csv' file that you created.
The data is added.

![](/exercises/Ex4/images/bpsampledata.png)  

Now we will **import** data from a file to **Incidents** entity.
Using a local text editor, create a local file called `incidents.txt`.
Add the following content to the file and save it locally:

```
ID,title,urgency_code,customer_BusinessPartner
3b23bb4b-4ac7-4a24-ac02-aa10cabd842c,Inverter not functional,H,1001036
3a4ede72-244a-4f5f-8efa-b17e032d01ee,No current on a sunny day,H,1001038
3ccf474c-3881-44b7-99fb-59a2a4668418,Strange noise when switching off Inverter,M,1001039
3583f982-d7df-4aad-ab26-301d4a157cd7,Solar panel broken,H,1001039
```

Rename your local file to `incidents.csv`.

From the editor, select **Incidents** and click **Import**.
From the file selection dialog box that opens, select the 'incidents.csv' file that you created.
The data is added.

![](/exercises/Ex4/images/incidentssample.png) 

For the last step, we will import data from a file to the **Conversations** entity.
Using a local text editor, create a local file called `conversations.txt`.
Add the following content to the file and save it locally:

```
ID,incidents_ID,timestamp,author,message
2b23bb4b-4ac7-4a24-ac02-aa10cabd842c,3b23bb4b-4ac7-4a24-ac02-aa10cabd842c,1995-12-17T03:24:00Z,Harry John,Can you please check if battery connections are fine?
2b23bb4b-4ac7-4a24-ac02-aa10cabd843c,3a4ede72-244a-4f5f-8efa-b17e032d01ee,1995-12-18T04:24:00Z,Emily Elizabeth,Can you please check if there are any loose connections?
9583f982-d7df-4aad-ab26-301d4a157cd7,3583f982-d7df-4aad-ab26-301d4a157cd7,2022-09-04T12:00:00Z,Sunny Sunshine, please check why the solar panel is broken
9583f982-d7df-4aad-ab26-301d4a158cd7,3ccf474c-3881-44b7-99fb-59a2a4668418,2022-09-04T13:00:00Z,Bradley Flowers,What exactly is wrong?
```

Rename your local file to `conversations.csv`.

From the editor, select **Conversations** and click **Import**.
From the file selection dialog box that opens, select the 'conversations.csv' file that you created.
The data is added.

![](/exercises/Ex4/images/conversationssample.png) 

## Summary

We have now added some sample data to two data models that we can use later to test the service that we will create.

Continue to [Exercise 5](../Ex5/README.md)

