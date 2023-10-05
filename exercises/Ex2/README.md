# Exercise 2 - Create a Data Model with CDS Graphical Modeler

In this exercise, we will use the new low-code perspective in the SAP Business Application Studio to create a service that persists our business data and exposes the data as an OData service for our consuming applications later on.
We will also test the service and see whether it runs or not.
## Exercise 2.1 Import CodeList to Data Model

In the storyboard, click on an entity under the **Data Models** tile, and click **Open in Graphical Modeler**. The CDS Graphical Modeler opens.

From the CDS Graphical Modeler editor's top right toolbar, click the (Show Details) icon.
Click the **Import** tab, click **+** (Import from other models) and select **Common Types**.
From the dialog box, select the **sap.common.CodeList** checkbox, and leave the other defaults.

The data type is imported to the model, it will be used later as a property in Urgency entity.

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
1. For the **Annotation Target**, select **title** from the dropdown-list.
2. For the **Annotation Value**, enter **Title**.
   
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
1. For the **Annotation Target**, select **cds.on.insert** from the dropdown list.
2. For the **Annotation Value**, select **$user** from the dropdown list.
   
Click **+** (Add) next to the **timestamp**.
1. For the **Annotation Target**, select **cds.on.insert** from the dropdown list.
2. For the **Annotation Value**, select **$now** from the dropdown list.

The entity is updated with the new annotations.

![](/exercises/Ex2/images/ConversationsAnnotations.png)

## Exercise 2.4 Add UrgencyCode Enum

In the CDS Graphical Modeler, click **+** and then select **Add Enum** from the dropdown list.
Change the tile's title to **UrgencyCode**.

![](/exercises/Ex2/images/UrgencyCodeEnum.png)

If not already open, click (Show Details) icon to open the **UrgencyCode** editor on the right-hand side.

In the UrgencyCode editor, click the **Properties** tab.
1. Select the **String** radio button.
2. Click **+** (Add property)   
3. For the **Enum Symbol** column, enter **High**.
4. For the **Enum Value** column, enter **H**.
5. Click **+** (Add property).   
6. For the **Enum Symbol** column, enter **Medium**.
7. For the **Enum Value** column, enter **M**.
8. Click **+** (Add property).   
9. For the **Enum Symbol** column, enter **Low**.
10. For the **Enum Value** column, enter **L**.
    
The UrgencyCode entity is updated with the new properties.

![](/exercises/Ex2/images/UrgencyCodeProperties.png)

## Exercise 2.5 Add Urgency Entity
Create the Urgency entity based on the UrgencyCode Enum, and add CodeList aspect.

In the CDS Graphical Modeler, click **Add Entity**.
Change the tile's title to **Urgency**.
Again, the **ID** property is created for you. This time however we will change it.

![](/exercises/Ex2/images/UrgencyEntity.png)

Click icon (Show Details), a new Urgency editor opens on the right-hand side.
In the Urgency editor, click the **Properties** tab.

1. Change the **ID** property to code.
3. Change the **UUID** type, to the previously created **UrgencyCode**.
3. For the rest of the columns, leave the default values.

The entity is updated with the new property.

![](/exercises/Ex2/images/UrgencyProperties.png)


## Exercise 2.6 Add Entity Relationship

Create associations between Incidents to Conversations and Urgency. An incident includes urgency, and multiple conversations.

1. Select the **Incidents entity** and click (Add Relationship) icon.
2. An arrow appears. Drag the arrow to the **Conversations** entity.
The **New Relationship** dialog box opens.
In the dialog box, fill in the following values:
1. For **Type**, select **Composition**.
2. For **Multiplicity**, select **To-Many**.
3. For the rest of the fields, leave the default values.
4. Click **Create**.
   
The Incidents entity is updated with the new relationship to Conversations.

![](/exercises/Ex2/images/IncidentsConversationRelationship.png)

1. Select the Incidents entity and click (Add Relationship) icon.
2. An arrow appears. Drag the arrow to the **Urgency** entity.
The **New Relationship** dialog box opens.
In the dialog box, fill in the following values:
1. For **Type**, select **Association**.
2. For **Multiplicity**, select **To-One**.
3. For the rest of the fields, leave the default values.
4. Click **Create**.
   
The Incidents entity is updated with the new relationship to Urgency.

![](/exercises/Ex2/images/IncidentsUrgencyRelationship.png)

## Summary

You've now created a data model including persistence in CAP (Cloud Application Programming model) that can be later used to be deployed to the SAP HANA database we will use. Note that you have not seen any CAP related commands or syntax.

Continue to - [Exercise 1.5](../ex1.5/README.md)
