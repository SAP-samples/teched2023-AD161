# Exercise 6 - Preview your service

We now have a service, we can preview it with sample data and with live data without having to deploy to the cloud. 

## Preview with Sample Data

From the left handed activity bar, click icon **Run Configurations**.
The run configuration editor opens.

Click the default run configuration: **Run incident_managementXXX-1**.
In the opened editor **OData** section the **Mock Data** is selected.

From the **Run Configurations** view, click icon **Run Module**.

![](/exercises/Ex6/images/runwithmock.png)

After a couple of seconds a new browser tab will be opened and you will see a screen like this:

![](/exercises/Ex6/images/previewlaunchpad.png) 

If you don't get a new tab, please check whether there is a blocker running in your browser. If so, please allow the domain of the Business Application Studio to open a new tab.

A preview of the service opens and the **ProcessorService** appears in the list of services on the right-hand side.
From the **Customers** raw, click icon **View as code** to preview the list of customers with the sample data.

Customers sample data is displayed.
The data is queried and exposed using OData V4. Please note that this service is run from an in-memory database that is automatically spun up for you during the preview, so any modification to the data will not persisted.

![](/exercises/Ex6/images/customermockresults.png)  


## Preview with Live Data

Now switch back to the tab that has the Business Application Studio with your project. We will now look at the second version of the preview which uses the live data. This time for the business partner the data is actually fetched from the S/4HANA Cloud system instead from the sample data.

To get there first press the **Stop Preview** button.

From the left handed activity bar, click icon **Run Configurations**.
The run configuration editor opens.

Click the run configuration: **API_BUSINESS_PARTNER**.
In the opened editor **OData** section the **Live Data** is selected.

From the Run Configurations view, click icon **Run Module**.

![](/exercises/Ex6/images/runlive.png)

After a couple of seconds a new browser tab will be opened and you will see a screen like this:

![](/exercises/Ex6/images/previewlaunchpad.png) 

If you don't get a new tab, please check whether there is a blocker running in your browser. If so, please allow the domain of the Business Application Studio to open a new tab.

A preview of the service opens and the **ProcessorService** appears in the list of services on the right-hand side.
From the **Customers** raw, click icon **View as code** to preview the list of customers.
This time you will get a lot more data than before, in addition the names are different, it is the real business partner data from the S/4 HANA backend

![](/exercises/Ex6/images/customerliveresults.png)  

## Summary
We have now previewed our service without any deployment.

Continue to - [Exercise 7](../Ex7/README.md)

