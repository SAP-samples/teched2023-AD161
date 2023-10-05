# Exercise 2 - Create a Data Model with CDS Graphical Modeler

In this exercise, we will use the new low-code perspective in the SAP Business Application Studio to create a service that persists our business data and exposes the data as an OData service for our consuming applications later on.
We will also test the service and see whether it runs or not.
## Exercise 2.1 Import CodeList to Data Model

In the storyboard, click on an entity under the **Data Models** tile, and click **Open in Graphical Modeler**. The CDS Graphical Modeler opens.

From the CDS Graphical Modeler editor's top right toolbar, click the (Show Details) icon.
Click the **Import** tab, click **+** (Import from other models) and select **Common Types**.
From the dialog box, select the **sap.common.CodeList** checkbox, and leave the other defaults.
The data type is imported to the model.

![](/exercises/Ex2/images/ImportCodeList.png)

## Exercise 2.2 Add Incidents Entity
Create the Incidents entity including its properties and annotations.

In the CDS Graphical Modeler, click **Add Entity**.
Change the tile's title to **Incidents**.
Note that the ID property as a key is already created for you for convenience reasons. One can choose to keep it or change / delete it, we keep it.
![](/exercises/Ex2/images/Incidents.png)

Click icon (Show Details), a new Incidents editor opens on the right-hand side.
In the Incidents editor, click the **Properties** tab, and then Click **+** (Add property).
For the **Name** column, enter the value **title**.
For the rest of the columns, leave the default values.
The entity is updated with the new property.

![](/exercises/Ex2/images/IncidentsProperties.png)

In the Incidents editor, click the **Annotations** tab.
Click  **+** (Add) next to the title.
For the **Annotation Target**, select **title** from the dropdown-list.
For the **Annotation Value**, enter **Title**.
The entity is updated with the new annotations.

![](/exercises/Ex2/images/IncidentsAnnotation.png)

## Exercise 2.3 Add Conversations Entity
Create the Conversations entity including its properties, annotations, and aspects.

In the CDS Graphical Modeler, click **Add Entity**.
Change the tile's title to **Conversations**.
![](/exercises/Ex2/images/ConversationsEntity.png)

Click icon (Show Details), a new Conversations editor opens on the right-hand side.
In the Conversations editor, click the **Properties** tab.
Click **+** (Add property):
1. For the **Name** column, enter the value **timestamp**, for the **Type** column, enter **DateTime**.
2. For the **Name** column, enter **author**.
3. For the **Name** column, enter **message**.
4. For the rest of the columns, leave the default values.
The entity is updated with the new properties.

![](/exercises/Ex2/images/ConversationsProperties.png)

In the Conversation editor, click the **Annotations** tab.
Click **+** (Add) next to the **author**.
For the **Annotation Target**, select **cds.on.insert** from the dropdown list.
For the **Annotation Value**, select **$user** from the dropdown list.
Click **+** (Add) next to the **timestamp**.
For the **Annotation Target**, select **cds.on.insert** from the dropdown list.
For the **Annotation Value**, select **$now** from the dropdown list.
The entity is updated with the new annotations.

![](/exercises/Ex2/images/ConversationsAnnotation.png)







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
