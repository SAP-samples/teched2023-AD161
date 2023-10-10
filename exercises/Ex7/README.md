# Exercise 7 - Create a List Report UI Application based on Fiori elements

After the creation of the service with several entities, we will create a list report with an object page based on the Fiori elements technology.

## Create a new UI Application

Go back to the **Storyboard** tab in the SAP Business Application Studio.
From **UI Applications** in the storyboard, click + (Add UI).
A UI Application wizard opens.

For the **UI Application Details**, enter **Incidents** for the **Display Name**.

For the **Data Source** select **ProcessorService**
Click **Next**.

![](/exercises/Ex7/images/UIApplicationDetails.png)


In the next step you can choose the technology you want to use to create your new UI app. You have a choice between "template based, responsive application" representing Fiori elements (FE) and "Mobile centric, freestyle application" representing the Mobile Development Kit (MDK).

For the **UI Application Type**, select **Template-Based, Responsive Application**, and click **Next**.

Some background that you can choose to skip reading:
Both create responsive apps that can be used on mobile devices and on desktops, however it is fair to say that with FE users rather start with desktops and MDK apps rather with mobile. Both adhere to templates, however in the MDK case it is a copy template that can be changed in whatever way the user wants to. FE is more restricted with respect to changes to the template, however the resulting app always adheres to the newest Fiori guidelines and comes with a lot of functionality out of the box.

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

Click **list Report** Page in the page map.

![](/exercises/ex4/images/LCAP_47.png)

You can now see the details of this page. Expand the **Columns** under **Table** and see the properties of your service entity. It looks like this:

![](/exercises/ex4/images/LCAP_48.png)

Click on the **category_ID** column and change its label to **category**, so the label looks nicer. Then under **Text** select **category/name**, this will configure the list to show the name of the category instead of its id.

![](/exercises/ex4/images/LCAP_48_2.png)

Click on the **BusinessPartner_BusinessPartner** column on the left, and change its label to **BusinessPartner**, again to make it look nicer

![](/exercises/ex4/images/LCAP_48_3.png)


## Adjust the Object Page of your UI Application and add Value Helps

Now press **Page Map** on the upper part of the editor to be taken back to the page map. Now edit the **Object Page**. Expand the **Fields** under **Form** in the **General Information** section. You can now see all the properties that were automatically added to the form.

For both, the association properties for the categoy and the business partner, we now want to change the label and enable value helps for them. 

To do this, first select property **category_id**, then in the panel that opens on the right, under **Label** change the text to **category**. Then below under **Display Type** select **Value Help**

![](/exercises/ex4/images/LCAP_49.png)

On the dialog, choose **name** for **Value Description Property** and then under **Text Arrangement** choose **Text Only**. Leave the **Display as Dropdown** option switched on and press **Apply**

![](/exercises/ex4/images/LCAP_49_2.png)

With this we have chosen to make to category field a dropdown (because it has a small number of entries the list doesn't get too long), to only show the name of the category and not its id. With the **Text Arrangement** option it would have been possible to also show its id in different orders of name and id.

After you have closed the dialog, still on the panel under **Text** select **category/name**, also press the button next to the field in the **Text Arrangement** box. This makes sure that not only the list in the dropdown shows the name and not an id but also in the field when an entry was selected, the pressing the button takes over the setting from the value help for the field as well.

![](/exercises/ex4/images/LCAP_49_3.png)

Now we will also carry out similar steps for the Business Partner. Only this time we will create a full blown value help instead of a dropdown because we expect the list of business partners from the backend to be too huge to handle in a dropdown.

Select property **BusinessPartner_BusinessPartner**, then in the panel on the right, under **Label** change the text to **BusinessPartner**. Then below under **Display Type** select **Value Help** again.

On the dialog, switch the **Display as Dropdown** option off, then press **Add Column** and select **FirstName**. Then do the same and add **LastName**. Finally press **Apply**

![](/exercises/ex4/images/LCAP_49_4.png)

Close the Page Editor and navigate back to **Home** tab.

## Summary
You have now added a new UI application to your project

Continue to - [Exercise 5](../ex5/README.md)

