# Exercise 6 - Preview Your Service

Now that we have a service, we can preview it with sample data and with live data without having to deploy to the cloud. 

## Preview with Sample Data

From the activity bar, on the left side, click the **Run Configurations** icon.
The run configuration editor opens.

Click the default run configuration: **Run incident_managementXXX-1**.

In the **OData** section the editor that opens, **Mock Data** is selected.

From the **Run Configurations** view, click the **Run Module** icon.

![](/exercises/Ex6/images/runwithmock.png)

After a couple of seconds, a new browser tab opens and a screen like this is displayed.

If you don't get a new tab, please check whether there is a blocker running in your browser. If so, please allow the domain of the Business Application Studio to open a new tab.

![](/exercises/Ex6/images/previewlaunchpad.png) 

If you don't get a new browser tab, check whether there is a blocker running in your browser. If there is a blocker, allow the domain of SAP Business Application Studio to open a new tab.

A preview of the service opens and the **ProcessorService** appears in the list of services on the right-hand side.
From the **Customers** row, click the **View as code** icon to preview the list of customers with the sample data.

Customers sample data is displayed.
The data is queried and exposed using OData V4. Please note that this service is run from an in-memory database that is automatically opened for you during the preview, so any modification to the data will not persisted.

![](/exercises/Ex6/images/customermockresults.png)  


## Preview with Live Data

Switch back to the tab that has SAP Business Application Studio with your project. We will now look at the second version of the preview, which uses live data. This time, the data for the business partner is actually fetched from the SAP S/4HANA Cloud system instead of from sample data.

To get there first press the **Stop Preview** button.

![](/exercises/Ex6/images/stoppreview.png)  

From the activity bar on the left side, click the **Run Configurations** icon.
The run configuration editor opens.

Click the run configuration: **API_BUSINESS_PARTNER**.
In the **OData** section of the editor that opens, **Live Data** is selected.

From the Run Configurations view, click the **Run Module** icon.

![](/exercises/Ex6/images/runlive.png)

After a couple of seconds, a new browser tab opens and a screen like this is displayed:

![](/exercises/Ex6/images/previewlaunchpad.png) 

If you don't get a new tab, check whether there is a blocker running in your browser. If so, allow the domain of SAP Business Application Studio to open a new tab.

A preview of the service opens and the **ProcessorService** appears in the list of services on the right-hand side.
From the **Customers** row, click the **View as code** icon to preview the list of customers.
This time you will get a lot more data than before. Also the names are different. This is the real business partner data from the SAP S/4HANA backend.

![](/exercises/Ex6/images/customerliveresults.png)  

Go to SAP Business Application Studio, press the **Stop Preview** button.

![](/exercises/Ex6/images/stoppreview.png)  



## Summary
We have now previewed our service without any deployment.

Continue to [Exercise 7](../Ex7/README.md)

