# Exercise 7 - Create a List Report UI Application

After creating a service with several entities, we will now create a list report with an object page, based on the SAP Fiori elements technology.

## Create a New UI Application

Go back to the **Storyboard** tab in SAP Business Application Studio.<br>
In the **UI Applications** tab, click + (Add UI).<br>
The UI Application wizard opens.<br>

In the **Display Name** field, enter **Incidents**.<br>
From the **Data Source** dropdown list, select **ProcessorService**.<br>
Click **Next**.<br>

![](/exercises/Ex7/images/UIApplicationDetails.png)

You can choose the technology you want to use to create your new UI app. You have a choice between a Template-based, responsive application" representing SAP Fiori elements (FE), and a "Mobile-centric, freestyle application" representing the Mobile Development Kit (MDK).

For the **UI Application Type**, click the **Template-Based, Responsive Application** tile, and then click **Next**.

Here's some background that you can choose to skip:
Both UI application types create responsive apps that can be used on mobile devices and on desktops. However, FE users would rather start with desktops and MDK apps rather than with mobile. Both adhere to the templates, however, in the MDK case, it is a template that can be changed in whichever way the user wants. FE is more restricted with respect to changes to the template.  However, the resulting app always adheres to the newest SAP Fiori guidelines and comes with a lot of functionality out-of-the-box.

![](/exercises/Ex7/images/templateresponsive.png)

For the **UI Application Template**, click the **List Report Page** tile, and then click **Next**.

![](/exercises/Ex7/images/listreport.png)

For the **Data Objects** step, fill in the following:

From the **Main entity** dropdown list,	select **Incidents**.<br>
From the **Navigation entity** dropdown list, select **None**.<br>
Click **Finish**.<br>

![](/exercises/Ex7/images/dataobjects.png)

And there you go, with just 4 steps you have created a complete UI app on top of your service entity. After a few seconds, the new UI app is displayed in the **UI Applications** tile of the **Storyboard** tab.<br>
After some more seconds, the **Page Map** editor pops up on the side, showing the pages that were generated for the UI app.

![](/exercises/Ex7/images/UIInStoryboard.png)

We now have a fully functional list report and an object page. Both pages are automatically populated with all the fields from our Incidents service entity, except for the ones that don't make sense. For example, the ID field that contains a UUID is not included, since showing UUIDs does not make for a good user experience.

While we could now already start testing our UI application and would get a nice application, we will first optimize the UI in a couple of places.

## Adjust the List Page of Your UI Application

From the **Page Map** editor, select the **List Report** tile, and click the **Configure Page** pencil icon.

![](/exercises/Ex7/images/configurelistreport.png)

You can now see the details of this page.<br>
Expand the **Columns** section under the **Table** section, and see the properties of your service entity. It should look like this:

![](/exercises/Ex7/images/listcolumns.png)

Click on **urgency_code**, and make the following updates on the right:

1. Change the **Label** to **Urgency** and click **Enter** to make the label look better. 

2. From the **Text** dropdown list, select **urgency/descr**.

3. From the **Text Arrangement** dropdown list, select **Text Only**. This will configure the list to show the description of the urgency instead of its code.

![](/exercises/Ex7/images/urgencycolumn.png)

Under **Table > Columns**, select **customer_BusinessPartner**.

Change the **Label** to **Customer** and press **Enter** to make the the label look better.

 ![](/exercises/Ex7/images/customercolumn.png)

Select **Table**.<br>
From the **Initial Load** dropdown list, select **Enabled**.

This enables an initial load of data so that you do not need to click the **Go** button to load it.

 ![](/exercises/Ex7/images/tableload.png)

## Adjust the Object Page of Your UI Application and Add Value Helps

Click **Page Map** on the upper part of the editor to go back to the page map.<br>
Select the **ObjectPage** tile and click the **Configure Page** pencil icon.

 ![](/exercises/Ex7/images/objectpage.png)

Select the **Header** section. <br>
From the **Title** dropdown list, select **title**, so that the incident title appears in the header.

 ![](/exercises/Ex7/images/headertitle.png)
 
Under the **Sections** section, select **General Information** to update the urgency and customer fields with label and value help.

From **General Information > Form > Fields**, select **urgency_code**.<br>

Then, in the panel that opens on the right, in the **Label** field, change the text to **Urgency**, and then press enter.<br>
From the **Text** dropdown list, select **urgency/descr**. <br>
From the **Text Arrangement** dropdown list, select **Text Only**. <br>
From the **Display Type** dropdown list, select **Value Help**.<br>

![](/exercises/Ex7/images/urgencycolumn.png)

The **Define Value Help Protperties** dialog box opens.

In the **Label** field, enter **Urgency**.<br>
From the **Value Description Property** dropdown list, select **descr**.<br>
From the **Text Arrangement** dropdown list, select **Text Only**.<br>


Leave the **Display as Dropdown** option switched on, and click **Apply**.<br>

 ![](/exercises/Ex7/images/urgencyvaluehelp.png)

Now we will carry out similar steps for the customer column.<br>
Only this time we will create a value help instead of a dropdown list because we expect the list of customers from the backend to be too huge to handle in a dropdown.<br>

From **General Information > Form > Fields**, select **customer_BusinessPartner**.<br>

In the panel that opens on the right, in the **Label** field, change the text to **Customer**, and press Enter.<br>
From the **Text** dropdown list, select **customer_BusinessPartner**. <br>
From the **Text Arrangement** dropdown list, select **Text Only**. <br>
From the **Display Type** dropdown list, select **Value Help**.<br>


[](/exercises/Ex7/images/customercolumnpage.png)

The **Define Value Help Protperties** dialog box opens.<br>
Switch off the **Display as Dropdown** option.<br>
Click **Add Column**.<br>
From the **Property** dropdown list, select **FirstName**.<br>  
Click **Add Column**.<br>
From the **Property** dropdown list, select **LastName**.<br>
Click **Apply**.<br>

![](/exercises/Ex7/images/customervaluehelp.png)

## Add the Conversations Section to the Object Page

Now we will add the **Conversations** section next to the **General Information**.<br>

Select **Sections**, click + (Add Sections), and select **Add Table Section**.<br>

The **Add Table Section** dialog box opens.<br>
In the **Label** field, enter **Conversations**, and press **Enter**.<br>
From the **Value Source** dropdown list, select **conversations**.<br>
Click **Add**.<br>

![](/exercises/Ex7/images/conversationaddsection.png)

Select **Conversations > Table > Columns**, click the + icon , and select **Add Basic Columns**.<br>

The **Add Basic Columns** dialog box opens.<br> 
From the **VColumns** dropdown list, select **author**, **timestamp**, and **message**.<br>
Click **Add**.<br>

![](/exercises/Ex7/images/conversationsaddcolumns.png)

Close the **Page Map** editor and navigate back to the **Storyboard** tab.

## Summary
You have now added a new UI application to your project.

Continue to [Exercise 8](../Ex8/README.md)

