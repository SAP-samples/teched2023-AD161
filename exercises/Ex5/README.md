# Exercise 5 - Create a Service (API)

After the creation of the data model (persistence layer), we will now select what to expose to the outside world as an API. This API can then be consumed by UI apps, workflows, etc. For this purpose, we will add several entities to a service. CAP will expose this service automatically as an OData service.

## Create New Service Entities

We will add 4 entities to the service: Customers, Incidents, Conversations, and Urgency.

Go back to the **Storyboard** tab in SAP Business Application Studio.

In the **Storyboard**, from the **Services** tile, click **ProcessorService**, and select **Open in Graphical Modeler**.
The CDS Graphical Modeler opens.

From the toolbar, click **Add Entity** and click **Entity1**.

The **New Projection** dialog box opens.

Select the **API_Busniess_Partner.A_BusinessPartner** entity, clear the **Enable draft editing** checkbox if not already cleared, and click **OK**.
The **A_BusinessPartner** entity appears in the CDS Graphical Modeler.

1. **IMPORTANT**: Change the name of the **A_BusinessPartner** entity to **Customers**.
2. Click the **Show Details** icon, and select the **Projection** tab.
3. Clear the **all properties** checkbox, and select the following properties:
   
   a. BusinessPartner
    
   b. FirstName
   
   c. LastName

 ![](/exercises/Ex5/images/customersprojection.png)  

From the toolbar, click **Add Entity**, and click **Entity1**.

The **New Projection** dialog box opens.

Select the **teched.Incidents** entity, make sure that the **Enable draft editing** checkbox is selected, and click **OK**.
The **Incidents** entity appears in the CDS Graphical Modeler.

![](/exercises/Ex5/images/incidentsprojection.png)

From the toolbar, click **Add Entity** and click **Entity1**.

The **New Projection** dialog box opens.

Select the **teched.Conversations** entity, clear the **Enable draft editing** checkbox, and click **OK**.
The **Conversations** entity appears in the CDS Graphical Modeler.

![](/exercises/Ex5/images/conversationsprojections.png)

From the toolbar, click **Add Entity** and click **Entity1**.

The **New Projection** dialog box opens.

Select the **teched.Urgency** entity, clear the **Enable draft editing** checkbox, and click **OK**.
The **Urgency** entity appears in the CDS Graphical Modeler.

![](/exercises/Ex5/images/urgencyprojection.png)
 
Make sure that the **ProcessorService** contains the 4 entities that you just added.

 ![](/exercises/Ex5/images/processorservice.png)  

## Summary
You have now added a **Processor** service to your project. Essentially, this service will expose your data model as an OData V4, RESTful API to your application.

Continue to [Exercise 6](../Ex6/README.md)
