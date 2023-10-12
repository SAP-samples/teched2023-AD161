# Exercise 8 - Add Application Logic to the Application
In this excercise we will add a logic of automatic urgency determination.
Customer may forget to select the urgency when creting an incident, so whenever an "urgent" appears in the title the incident will automaticaly marked as urgent.

## Update Incident from Incident's Title

From the **Storyboard**, select the **ProcessorService** and click **Open in Graphical Modeler**.
The CDS Graphical Modeler opens.

Select the **Incidents** entity and click icon (Add Logic).

The Add Application Logic dialog box opens.
From the dialog box:
For the Service Entity field, make sure that the ProcessorService.incidents value is selected.
For the Name field, enter changeUrgencyDueToSubject for the value.
Click Add.
The application logic editor opens.
From the CONFIGURATION tab of the application logic editor, select the following options:
In the Phase section, select Before.
In the Standard Event section, select both, Create and Update.
Click Open Code Editor > Application Logic.
The application logic handler file opens.
In the 'changeUrgencyDueToSubject.js' file, after the comment Your code here, add the following content:

const incident = request.data;
if (incident.title?.toLowerCase().includes("urgent")) {
      incident.urgency = { 
        code: "H",
        descr: "High"
      };
}
Now we need to add the logic part. 
For this, on the **Home** page, in the **Service** tile choose the **Capex**  again. On the graphical modeler, invoke the menu by clicking on the header of **Capex** and select the **Add Logic** command.

![](/exercises/ex6/images/LCAP_64.png)

Now there will be a dialog for you to enter a service entity (which we already have chosen, it is the **Capex** one) and a name for the new handler. The one that the system suggests is fine, take it all over by pressing the **Add** button:

![](/exercises/ex6/images/LCAP_64-2.png)

One the following screen you can specify when the new handler should be invoked. Ours should be invoked **After** there was a **Read** request for the **Capex** entity. Select these properties and then press the **Open JS Editor** button:

![](/exercises/ex6/images/LCAP_64-3.png)

Now a new text file is opened. It already contains the stub for our handler function. Replace the line:

```Javascript
    // Your code here
```

with:

```Javascript
    const capexs = Array.isArray(context.results) ? context.results : [context.results];
    capexs.forEach(capex => {
        if (capex.totalcost > 200) {
            capex.criticality = 1;
        } else {
            capex.criticality = 2;
        }
    });
```

so that you finally see:

![](/exercises/ex6/images/LCAP_65.png)

Save the file.

Let's have a look what happens in the code. As set up, the function is invoked after the was a read request for the **Capex** entity. The request could for example be created as an OData GET request from the browser. The CAP framework invokes our custom handler and passes the data into it, that it has just retrieved from the data base. It might be one or more entities. Our code looks into the data, it looks whether **totalcost** is greater than 200, if so, it sets our new **criticality** property to 1 otherwise to 2.

So, with this, the criticality is set according to the total cost of our Capex express.

## Adjust the UI based on the Application Logic

We now need to adjust our UI application making use of the values in Capex's **criticality** property. We are going to use the **totalcost** field on the UI to change its look depending on the value of the criticality.

To do this, switch back to the **Home** tab. Under **User Interfaces**, click on your **My List Report** application. The **Page Map** opens, for the **List Report** page, invoke the pencil shaped icon to configure the page. Expand the **Table** and then the **Columns** entry and select the **totalcost** property.

Look for the **Criticality** box under the properties of **totalcost**. We can use it to display the criticality of the totalcost. If you expand the dropdown here, you find a list of the property of the **Capex** entity. Choose the criticality one. Note, the criticality functionality is called like we have called our service entity's property, but we could have chosen any other name for the property as well.

![](/exercises/ex6/images/LCAP_66.png)

After a couple of seconds after you have selected the **critiality** property, a new **Criticality Representation** box appears. Here we can configure how the criticality is visually represented, with just a color, with an addition icon or not at all. In our case, we want to add an icon as well to a color change, so choose the **With Icon** entry

![](/exercises/ex6/images/LCAP_67.png)

## Preview the Application

We have now finished configuring the application and we can preview it again.

Go back to the **Home** tab and on the **Preview** button in the upper right part of the screen, select **With Live Data**. As before after a couple of seconds the **Project Preview** page comes up. Click on the **My List Report** application again. It should come up as before. Click on its **Create** button above the empty list.

Fill out the form, pick any *BusinessPartner** from the value help and any **Category** from the dropdown and fill in a **description** of your choice. Make sure that for this first request you choose a value for **totalcost** which is *smaller* than the threshold in our application handler code, so smaller than **200**

![](/exercises/ex6/images/LCAP_68.png)

Press the **Create** button at the bottom of the page to save the data. Then press the **<** button in the top left part of the screen to return to the list page. Here press the **Go** button and your new entry should appear in the list. Not how the text in the **totalcost** column is now yellow and has a warning icon with it, indicating a criticality of lower priority.

![](/exercises/ex6/images/LCAP_69.png)

Now press **Create** again to add a second entry. This time make sure that you choose a value that is **greater** than 200. After you have saved the entry and returned to the list page you should see the new entry also, colored in red and with an appropriate icon, indicating the highest criticality:

![](/exercises/ex6/images/LCAP_60.png)

## Summary
We have now added application logic to the application. We have learned that using the low code tools, one can switch to normal textual editors to change / add code.

Continue to - [Exercise 7](../ex7/README.md)
