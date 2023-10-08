# Exercise 3 - Reference an S/4HANA Cloud Service in your Data Model

In this exercise, we will add an S/4HANA Cloud service, the Business Partner to our project and associate it with our incident management model

## Exercise 3.1 Discover an S/4HANA Cloud Service and add it to your Data Model

From the **Storyboard** press "+" on the **External Resources** tile. This opens the **Service Center** on the left hand side.

![](/exercises/Ex3/images/externalresources.png)

There you can see a choice of **SAP System**. Technically these are destinations to OData Services in your backend system that an administrator has set up for you. These can be services from an S/4HANA system or from other SAP backend systems.

Expand **SAP System > lcapteched** and select **API_BUSINESS_PARTNER**.

You can now see the details of the chosen Service, its entities and the properties for each entity, as well general data about the service.
Press on the **Add External Data Model** in the upper right corner of the screen.
This adds the chosen Service to you project.

![](/exercises/Ex3/images/businesspartner.png)

Return to **Storyboard**, after a couple of seconds the new Service will show up on the **External Resources** tile.

![](/exercises/Ex3/images/bpinstoryboard.png)

## Exercise 3.5.2 Associate a Business Partner Entity with the Incidents Entity

On **Storyboard** under **Data Models** click **Open in Graphical Modeler** to get back into the graphical modeler.

Here invoke the **Add Relationship** function on **Incidents** again.

![](/exercises/Ex3/images/addbprelationship.png)

This is to create a new association to a Business Partner entity. However, we don't see the Business Partner on the canvas. This is because it is in another namespace than our own Incidents entity.

Therefore, drag the end of line of the relationship to an empty space on the canvas and click the mouse button.

A new dialog will come up. From the dropdown choose **Target Entity Type** **API_BUSINESS_PARTNER-A_BusinessPartner**. Change the suggested **Property Name** to **customer**. Leave all the other suggestions (**Association** and **To-One**) as they are and press **Create**

![](/exercises/Ex3/images/incidentcustomerrelationship.png)

You will now see the final data model:

![](/exercises/Ex3/images/bprelationshipcreated.png)


## Summary

You've now added a reference to incidents data model a customer relationship from a service in an S/4HANA Cloud backend system.

Continue to - [Exercise 4](../Ex4/README.md)