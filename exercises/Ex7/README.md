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
Both UI application types create responsive apps that can be used on mobile devices and on desktops. However, FE users would rather start with desktops and MDK apps rather with mobile. Both adhere to the templates, however in the MDK case it is a template that can be changed in whatever way the user wants to. FE is more restricted with respect to changes to the template, however the resulting app always adheres to the newest SAP Fiori guidelines and comes with a lot of functionality out of the box.

![](/exercises/Ex7/images/templateresponsive.png)

For the **UI Application Template**, select **List Report Page** and click **Next**.

![](/exercises/Ex7/images/listreport.png)

For the **Data Objects**, select the following values:

For **Main entity**,	select **Incidents**.
For **Navigation entity**, select **None**.
Click **Finish**.

![](/exercises/Ex7/images/dataobjects.png)

And there you go, with just 4 steps you have created a complete UI app on top of your service entity. After a few seconds, the new UI app is displayed in the **UI Applications** tile of the **Storyboard** tab. After some more seconds, the **Page Map** editor pops up on the side, which shows the pages that are generated for the UI app.

![](/exercises/Ex7/images/UIInStoryboard.png)

We now have a fully functional list report and an object page. Both pages are automatically populated with all the fields from our Incidents service entity, except for the ones that don't make sense. For example, the ID field that contains a UUID is not included, since showing UUIDs does not make a good user experience.

While we could now already start testing our UI application and would get a nice application, we will first optimize the UI in a couple of places.

## Adjust the List Page of Your UI Application

From the Page Map editor, select the **List Report** tile and click the **Configure Page** pencil icon.

![](/exercises/Ex7/images/configurelistreport.png)

You can now see the details of this page. Expand the **Columns** under **Table** and see the properties of your service entity. It should look like this:

![](/exercises/Ex7/images/listcolumns.png)

Under **Table > Columns**, select **urgency_code** and make the following updates on the right:

1. Change the **Label** to **Urgency** and press **Enter** to make the label looks better. 

2. For the **Text** field, select **urgency/descr**.

3. For the **Text Arrangement** field, select **Text Only**. This will configure the list to show the description of the urgency instead of its code.

![](/exercises/Ex7/images/urgencycolumn.png)

Under **Table > Columns**, select **customer_BusinessPartner**.

Change the **Label** to **Customer** and press **Enter** to make the the label look better.

 ![](/exercises/Ex7/images/customercolumn.png)

Select **Table** and for the **Initial Load** field, select **Enabled**.

This enables an initial load of data and the you do not need to click the **Go** button to load data.

 ![](/exercises/Ex7/images/tableload.png)

## Adjust the Object Page of Your UI Application and Add Value Helps

Now press **Page Map** on the upper part of the editor to go back to the page map.
From the **Page Map** editor, select the **IncidentsObjectPage** tile and click the **Configure Page** pencil icon.

 ![](/exercises/Ex7/images/objectpage.png)

Select the **Header** section. For the **Title** input field, select **title**, so that the incident title will be located in the header.

 ![](/exercises/Ex7/images/headertitle.png)
 
Select the **General Information** to update the urgency and customer fields with label and value help.

From **General Information > Form > Fields**, select **urgency_code**.

Then in the panel that opens on the right, under **Label** change the text to **Urgency** and press enter.
For the **Text** property select the **urgency/descr** value. 
For the **Text Arrangement** property select the **Text Only** value . 

Then,under **Display Type** select **Value Help**.

![](/exercises/Ex7/images/urgencycolumn.png)

In the dialog box, enter **Urgency** in the **Label** field, choose **descr** for the **Value Description Property** and then under **Text Arrangement** choose **Text Only**.

Leave the **Display as Dropdown** option switched on and press **Apply**.

 ![](/exercises/Ex7/images/urgencyvaluehelp.png)

Now we will carry out similar steps for the customer column.
Only this time we will create a value help instead of a dropdown list because we expect the list of customers from the backend to be too huge to handle in a dropdown.

From **General Information > Form > Fields**, select **customer_BusinessPartner**.

In the panel that opens on the right, under **Label** change the text to **Customer** and press enter.
For the **Text** property select the **customer_BusinessPartner** value. 
For the **Text Arrangement** property select the **Text Only** value. 

Then, under **Display Type** select **Value Help**.

[](/exercises/Ex7/images/customercolumnpage.png)

In the dialog box, switch the **Display as Dropdown** option off, press **Add Column**, and select **FirstName**. Then add column **LastName**. Press **Apply**

![](/exercises/Ex7/images/customervaluehelp.png)

## Add the Conversations Section to the Object Page

Now we will add the **Conversations** section next to the **General Information**.
Select **Sections**, click + (Add Sections), and select **Add Table Section**.

In the dialog box that opens, perform the following steps:
Fill in **Conversations** as the **Label** and press **Enter**.
Select **conversations** as the **Value Source**.
Click **Add**.

![](/exercises/Ex7/images/conversationaddsection.png)

Select **Conversations > Table > Columns**, click the + icon , and select **Add Basic Columns**.

In the dialog box that opens, select **author**, **timestamp**, **message**, and click **Add**.

![](/exercises/Ex7/images/conversationsaddcolumns.png)

Close the **Page Map** editor and navigate back to the **Storyboard** tab.

## Summary
You have now added a new UI application to your project

Continue to [Exercise 8](../Ex8/README.md)

