# Exercise 7 - Create a List Report UI Application

After creating a service with several entities, we will now create a list report with an object page, based on the SAP Fiori elements technology.

## Create a New UI Application

Go back to the **Storyboard** tab in SAP Business Application Studio.
From **UI Applications** in the storyboard, click + (Add UI).
A UI Application wizard opens.

For the **UI Application Details**, enter **Incidents** for the **Display Name**.

For the **Data Source** select **ProcessorService**
Click **Next**.

![](/exercises/Ex7/images/UIApplicationDetails.png)

In the next step you can choose the technology you want to use to create your new UI app. You have a choice between a Template-based, responsive application" representing SAP Fiori elements (FE) and a "Mobile-centric, freestyle application" representing the Mobile Development Kit (MDK).

For the **UI Application Type**, select **Template-Based, Responsive Application**, and click **Next**.

Here's Some background that you can choose to skip reading:
Both UI application types create responsive apps that can be used on mobile devices and on desktops. However, FE users would rather start with desktops and MDK apps rather with mobile. Both adhere to the templates, however in the MDK case it is a copy template that can be changed in whatever way the user wants to. FE is more restricted with respect to changes to the template, however the resulting app always adheres to the newest SAP Fiori guidelines and comes with a lot of functionality out of the box.

![](/exercises/Ex7/images/templateresponsive.png)

For the **UI Application Template**, select **List Report Page** and click **Next**.

![](/exercises/Ex7/images/listreport.png)

For the **Data Objects**, select the following values:

For **Main entity**	select **Incidents**.
For **Navigation entity** select **None**.
Click **Finish**.

![](/exercises/Ex7/images/dataobjects.png)

And there you go, with just 4 steps you have created a complete UI app on top of your service entity. After some seconds you will see the new UI app showing up in the **UI Applications** tile on the **Storyboard** tab. After some more seconds an editor pops up to the side which shows the pages that are generated for the UI app, the so-called **Page Map**.

![](/exercises/Ex7/images/UIInStoryboard.png)

We now have a fully functional list report and and object page. Both pages are automatically populated with all the fields from our Incidents service entity apart from the ones that don't make sense: the ID field which contains a UUID is not included, as showing UUIDs to humans is not a good user experience.

While we could now already start testing our UI application and would get a nice application, we will optimize the UI at a couple of places.

## Adjust the List Page of your UI Application

From the Page Map editor, select the **List Report** tile and click the pencil icon **Configure Page**.

![](/exercises/Ex7/images/configurelistreport.png)

You can now see the details of this page. Expand the **Columns** under **Table** and see the properties of your service entity. It looks like this:

![](/exercises/Ex7/images/listcolumns.png)

Under **Table > Columns**, select **urgency_code** and make the following updates on the right:

1. Change the **Label** to **Urgency** and press **Enter**, so the label looks nicer. 

2. For **Text** field, select **urgency/descr**.

3. For **Text Arrangement** field, select **Text Only**, this will configure the list to show the description of the urgency instead of its code.

![](/exercises/Ex7/images/urgencycolumn.png)

Under **Table > Columns**, select **customer_BusinessPartner**.

Change the **Label** to **Customer** and press **Enter**, again to make it look nicer.

 ![](/exercises/Ex7/images/customercolumn.png)

Select **Table**, for the **Initial Load** field, select **Enabled**.

This enables an initial load of data and the user does not need to click the Go button.

 ![](/exercises/Ex7/images/tableload.png)

## Adjust the Object Page of your UI Application and add Value Helps

Now press **Page Map** on the upper part of the editor to be taken back to the page map.
From the **Page Map** editor, select the **IncidentsObjectPage** tile and click the pencil icon **Configure Page**.

 ![](/exercises/Ex7/images/objectpage.png)

Select **Header** section, for the **Title** input field, select **title**, so that incident title will be located in the header.

 ![](/exercises/Ex7/images/headertitle.png)
 
Select the **General Information** to update urgency and customer fields with label and value help.

From **General Information > Form > Fields**, select **urgency_code**.

Then in the panel that opens on the right, under **Label** change the text to **Urgency** and press enter.
For **Text** property select the value **urgency/descr**. 
For **Text Arrangement** property select the value **Text Only**. 

Then below under **Display Type** select **Value Help**.

![](/exercises/Ex7/images/urgencycolumn.png)

On the dialog, fill **Urgency** in **Label** field, choose **descr** for **Value Description Property** and then under **Text Arrangement** choose **Text Only**.

Leave the **Display as Dropdown** option switched on and press **Apply**.

 ![](/exercises/Ex7/images/urgencyvaluehelp.png)

Now we will also carry out similar steps for the customer column.
Only this time we will create a full blown value help instead of a dropdown because we expect the list of customers from the backend to be too huge to handle in a dropdown.

From **General Information > Form > Fields**, select **customer_BusinessPartner**.

Then in the panel that opens on the right, under **Label** change the text to **Customer** and press enter.
For **Text** property select the value **customer_BusinessPartner**. 
For **Text Arrangement** property select the value **Text Only**. 

Then below under **Display Type** select **Value Help**.

[](/exercises/Ex7/images/customercolumnpage.png)

On the dialog, switch the **Display as Dropdown** option off, then press **Add Column** and select **FirstName**. Then do the same and add **LastName**. Finally press **Apply**

![](/exercises/Ex7/images/customervaluehelp.png)

## Add Conversation section to the Object Page

Now we will add the **Conversations** section is next to the **General Information**.
Select **Sections**, click + (Add Sections), and select **Add Table Section**.

In the dialog box that opens, perform the following steps:
Fill in **Conversations** as the **Label**, click **Apply**.
Select **conversations** as the **Value Source**.
Click **Add**.

![](/exercises/Ex7/images/conversationaddsection.png)

Select **Conversations > Table > Columns**, click + icon , and select **Add Basic Columns**.

In the dialog box that opens, select **author**, **timestamp**, **message**, and click **Add**.

![](/exercises/Ex7/images/conversationsaddcolumns.png)

Close the Page Editor and navigate back to **Storyboard** tab.

## Summary
You have now added a new UI application to your project

Continue to - [Exercise 8](../Ex8/README.md)

