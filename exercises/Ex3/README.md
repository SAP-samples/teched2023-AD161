# Exercise 3 - Reference an SAP S/4HANA Cloud Service in Your Data Model

In this exercise, we will add an SAP S/4HANA Cloud service, the Business Partner, to our project and associate it with our incident management model.

## Exercise 3.1 Discover an SAP S/4HANA Cloud Service and Add it to Your Data Model

From the **Storyboard**, click "+" on the **External Resources** tile. This opens the **Service Center** on the left-hand side.

![](/exercises/Ex3/images/externalresources.png)

There, you can see the **SAP System** node. Technically, it contains destinations to OData services in your backend system that an administrator has set up for you. These can be services from an SAP S/4HANA system or from other SAP backend systems.

Expand **SAP System > lcapteched**, and select **API_BUSINESS_PARTNER**.

You can now see the details of the chosen service, its entities, the properties for each entity, and general data about the service.<br>
Click **Add External Data Model** in the upper-right corner of the screen.<br>
This adds the chosen service to you project.

![](/exercises/Ex3/images/businesspartner.png)

Return to the **Storyboard**. After a couple of seconds, the new service is displayed in the **External Resources** tile.

![](/exercises/Ex3/images/bpinstoryboard.png)

## Exercise 3.5.2 Associate a Business Partner Entity with the Incidents Entity

From the **Storyboard**, under **Data Models**, select an entity and click **Open in Graphical Modeler** to get back to the graphical modeler.

From the **Incidents** entity, click  the **Add Relationship** icon.<br>
Drag the end of line of the relationship to an empty space on the canvas and click the mouse button.

![](/exercises/Ex3/images/addbprelationship.png)

This creates a new association to a Business Partner entity. However, we don't see the Business Partner on the canvas. This is because it is in a different namespace than our own Incidents entity.

A new dialog appears.<br>
1. From the **Target Entity** dropdown list, select **API_BUSINESS_PARTNER-A_BusinessPartner**. <br>
2. Change the suggested **Property Name** to **customer**. <br>
3. Leave all the other suggestions (**Association** and **To-One**) as they are, and click **Create**.

![](/exercises/Ex3/images/incidentcustomerrelationship.png)

You can now see the final data model:

![](/exercises/Ex3/images/bprelationshipcreated.png)


## Summary

You have added an external reference to the SAP S/4HANA Cloud backend system and connected it to your **Incidents** data model.

Continue to [Exercise 4](../Ex4/README.md).
