# Exercise 6 - Preview your service

We now have a service, we can preview it with sample data and with live data without having to deploy to the cloud. 

## Preview with Sample Data

From the left handed activity bar, click icon **Run Configurations**.
The run configuration editor opens.

Click the default run configuration: **Run incident_managementXXX-1**.

From the Run Configurations view, click icon **Run Module**.

![](/exercises/Ex6/images/runwithmock.png)

After a couple of seconds a new browser tab will be opened and you will see a screen like this:

![](/exercises/Ex6/images/previewlaunchpad.png) 

If you don't get a new tab, please check whether there is a blocker running in your browser. If so, please allow the domain of the Business Application Studio to open a new tab.

A preview of the service opens and the ProcessorService appears in the list of services on the right-hand side.
From the **Customers** raw, click icon **View as code** to preview the list of customers with the sample data.

Customers sample data are displayed.
The data is queried and exposed using OData V4. Please note that this service is run from an in-memory database that is automatically spun up for you during the preview, so any modification to the data will not persisted.

![](/exercises/Ex6/images/customermockresults.png)  


## Preview with Live Data

Now switch back to the tab that has the Business Application Studio with your project. We will now look at the second version of the preview which uses the live data. This time for the business partner the data is actually fetched from the S/4 HANA Cloud system instead from the sample data. For the categories though, where there is no backend connection still the sample data will be shown.

To get there first press the **Stop Preview** button.

![](/exercises/ex5/images/LCAP_59.png)

The button changes to become a **Preview** button. This time select the **With Live Data** option. After some seconds again the **Application Development Preview Page** comes up and looks like the one before. However if you again press the rightmost button next to **BusinessPartner** you will get a lot more data than before, it is the real business partner data from the S/4 backend:

![](/exercises/ex5/images/LCAP_510.png)

Similarly if you follow all the steps in your **My List Report** application like before you will get the backend data in the business partner value help:

![](/exercises/ex5/images/LCAP_511.png)

You can play around with the already built in filters for the data as well.

## Summary
We have now previewed our new application without any deployment.

Continue to - [Exercise 6](../ex6/README.md)

