# Exercise 5 - Create a Service (API)

After the creation of the data model ( persistence layer ) we will now select what to expose to the outside world as an API. This API can then be consumed by UI apps, workflows, etc.. For this we will add several entities to a service. CAP will expose this service automatically as a full blown OData service.

## Create New Service Entities

Go back to the **Storyboard** tab in SAP Business Application Studio.

In the **Storyboard**, from the Services tile, click the **ProcessorService** and select **Open in Graphical Modeler**.
The CDS Graphical Modeler opens.

From the toolbar, click **Add Entity** and click **Entity1**.
The **Select Projection Type** dialog box opens.
Select the **Incidents entity**, make sure that the **Enable draft editing** checkbox is selected, and click **OK**.
The Incidents entity appears in the CDS Graphical Modeler.

![](/exercises/Ex5/images/incidentsprojection.png)

From the toolbar, click **Add Entity** and click **Entity1**.
The **Select Projection Type** dialog box opens.
Select the **Conversations** entity, clear the **Enable draft editing** checkbox, and click **OK**.
The Conversations entity appears in the CDS Graphical Modeler.

![](/exercises/Ex5/images/conversationsprojections.png)

From the toolbar, click **Add Entity** and click **Entity1**.
The **Select Projection Type** dialog box opens.
Select the **Urgency** entity, clear the **Enable draft editing** checkbox, and click **OK**.
The Urgency entity appears in the CDS Graphical Modeler.

![](/exercises/Ex5/images/urgencyprojections.png)

From the toolbar, click **Add Entity** and click **Entity1**.
The **Select Projection Type** dialog box opens.
Select the **A_BusinessPartner** entity, clear the **Enable draft editing** checkbox, and click **OK**.
1. Rename the the **A_BusinessPartner** to **Customers**.
2. Click icon **Show Details**, and select **Projection** tab.
3. Uncheck **all properties**, and select the following properties:
   
   a. BusinessPartner
   
   b. Customer
   
   c. FirstName
   
   d. LastName

Go back to the storyboard and make sure that the ProcessorService contains the 4 entities you just added.

![](/exercises/Ex5/images/customersprojections.png)


![](/exercises/ex3/images/LCAP_32.png)

Add another entity and repeat the step to create another service entity. This time select the type **LCAPXXX.Category** and find the name **Category** after selection. Click **Create**

Again we have exposed our **Category** data model 1:1. The types of service entities make a lot of sense if for example you want to create a new UI form to maintain Capex data and in the UI's **Category** field you want to expose a value help / dropdown of all the categories. That's actually what we are going for! In such a case you need a different entity for what you want to present in the value help and that's why we expose **Category** as well.

Add a third entity, this time choose **API_BUSINESS_PARTNER.A_BusinessPartner**. The Business Partner entity comes with a lot of properties though, a lot of these we don't really need for our application and therefore, we don't want to expose them all in the new service. Therefore, we will just select some of them. To get to this, first uncheck the first entry in the list, the **<all properties>** property. Now select the properties:
- **Business Partner**
- **FirstName**
- **LastName**

Also change the **Name** to be **BusinessPartner**
## Summary
You have now added a service to your project. Essentially, this service will expose your data model as an OData V4, RESTful API to your application.

Continue to - [Exercise 6](../Ex6/README.md)
