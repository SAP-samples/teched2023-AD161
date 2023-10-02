# Exercise 1 - Create a data model with the SAP Business Application Studio

In this exercise, we will use the new low-code perspective in the SAP Business Application Studio to create a service that persists our business data and exposes the data as an OData service for our consuming applications later on.
We will also test the service and see whether it runs or not.

## Exercise 1.1 Launch Low-Code Perspective

Open your browser and launch the so-called "lobby" using the following URL:
```URL
https://lcapteched-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/lobby
```
You should see the central entry for low-code / no-code development on SAP BTP.

![](/exercises/ex1/images/lobby_01.png)

Click on the "Create" button and select "Business an Application". 

![](/exercises/ex1/images/lobby_02.png)

On the next sreen, choose the entry for "Pro Developers".

![](/exercises/ex1/images/lobby_03.png)

A dialog appears where you can enter the following name for your project. As we plan to deploy our project it is important to stick to the naming convention here.  

**DO NOT USE YOUR OWN PROJECT NAME**  

Name your project   
```
LCAPXXX
```
Where XXX is the user number that was assigned to you. Please make sure that you got a user number assigned by the speakers / moderators, don't make up your own number to avoid clashes with the deployments of others. So if your user number is for example **008** your project name is **LCAP008**

You can provide any descriptive text if you want.  
Confirm with a click on **Create**.

After the SAP Business Application Studio has created your environment you should see a screen like this (depending on whether your dev space has already started, this might take several minutes to come up). Make sure you select the **Home** tab (you might see **Guided Development** first):
![](/exercises/ex1/images/LCAP_01.png)

Now we can build our project and use SAP-opinionated technologies such as CAP (Cloud Application Programming Model), Fiori Elements and MDK (Mobile Development Kit) for our purposes without thinking about how to structure our project and being able to concentrate on the tasks to solve rather than spending time to think about project setup and wiring up technologies.

In the next step we will create a data model.

## Exercise 1.2 Create a Data Model

We will first create our persistence by adding a data model to our project. You can use the **Data Models** tile for that.

Create your first data model ( = entity ) which is the one that contains all the properties that should pop up in the UI apps to create and view registrations for expenditures. Note that the ID property as a key is already created for you for convenience reasons. One can choose to keep it or change / delete it, we keep it.

Entity Name: Capex

| Property Name | Property Type | Key Property
| ----------- | ----------- | - |
| ID | UUID | X |
| description | String |   |
| totalcost | Integer |   |

![](/exercises/ex1/images/LCAP_02.png)


We will now add another entity. This time we will create a **Category** entity, which will contain some categories in which a Capex request will fall. This time in the same editor, press the **Add Entity** button at the top, move the box anywhere where you like on the canvas and then type in the name **Category**. Then click on the header of the box, this will invoke a menu to the right. Select the **Edit** button:

![](/exercises/ex1/images/LCAP_02-01.png)

Now enter the following:

Entity Name: Category

| Property Name | Property Type |
| ----------- | ----------- |
| ID | Integer | X |
| name | String |   |

Again, the **ID** property is created for you. This time however, make sure you change its property type from **UUID** to **Integer**.

Now the data model will look like this:

![](/exercises/ex1/images/LCAP_03.png)

We will now create a relationship (association) between the entities to indicate category for a capex request.

Click on the header area of the **Capex** entity and click "Add Relationship" in the menu that appears:

![](/exercises/ex1/images/LCAP_04.png)

Associate your **Capex** entity with the **Category** entity by dropping the arrow on the **Category** box and then take over the suggested values as they are really what we need here: a **to one association** from **Capex** to **Category**:

![](/exercises/ex1/images/LCAP_05.png)

Our data model should now look like this:

![](/exercises/ex1/images/LCAP_06.png)

## Summary

You've now created a data model including persistence in CAP (Cloud Application Programming model) that can be later used to be deployed to the SAP HANA database we will use. Note that you have not seen any CAP related commands or syntax.

Continue to - [Exercise 1.5](../ex1.5/README.md)
