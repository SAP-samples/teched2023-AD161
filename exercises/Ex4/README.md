# Exercise 4 - Add some sample data

We will now populate our data model with some sample data so that we can test our service. Note, that even though it says sample data, the data can be of two types:
- fixed values that are part of you application and should be deployed along with the application. An example could be the data for **Urgency** if there is only a fixed set of urgencies that cannot be changed
- sample data that is really only used to test the services and applications that you create and that should not be part of a productive deployment

Go to the **Storyboard** and from the **Data Models** tile, click the **Urgency** entity and select **Add Sample Data**.
The Sample Data Editor opens.

From the editor, select **Urgency**.
Change the **Mock Data** switch to **Off** and enter 3 as the number of rows.
Click **Add**:
In the descr field, enter Low, Medium and High accordingly.

![](/exercises/Ex4/images/urgencysampledata.png)  

From the editor, select **A_BusinessPartner**
This time change the **Mock Data** switch to **On** and enter 5 as the number of rows.  Now there are 5 entries created and the data with it, you should see something like this:

![](/exercises/Ex4/images/bpsampledata.png)  


Using a local text editor, create a local file called `incidents.txt`.
Add the following content to the file and save it locally:

ID,customer_ID,title,urgency_code,status_code
3b23bb4b-4ac7-4a24-ac02-aa10cabd842c,8fc8231b-f6d7-43d1-a7e1-725c8e988d18,Inverter not functional,H,C
3a4ede72-244a-4f5f-8efa-b17e032d01ee,feb04eac-f84f-4232-bd4f-80a178f24a17,No current on a sunny day,H,N
3ccf474c-3881-44b7-99fb-59a2a4668418,feb04eac-f84f-4232-bd4f-80a178f24a17,Strange noise when switching off Inverter,M,N
3583f982-d7df-4aad-ab26-301d4a157cd7,2b87f6ca-28a2-41d6-8c69-ccf16aa6389d,Solar panel broken,H,I

Rename your local file to `incidents.csv`.

From the editor, select **Incidents** and click **Import**.
From the file selection dialog box that opens, select the 'incidents.csv' file that you created.
The data is added.
Fill the **customer** column value from the dropdown.

![](/exercises/Ex4/images/incidentssample.png)  



This time change the **Mock Data** switch to **On** and enter 5 as the number of rows.  Now there are 5 entries created and the data with it, you should see something like this:

![](/exercises/Ex4/images/bpsampledata.png)  
We have now added the sample data that we need. We could have of course also added sample data for the Capex entity as well, but in this project we rather create its data with the resulting application.

## Summary

We have now added some sample data to two data models that we can later use to test the service we are going to create.

Continue to - [Exercise 3](../ex3/README.md)

