# Exercise 8 - Add Application Logic to the Application
In this excercise we will add a logic of automatic urgency determination.
Customer may forget to select the urgency when creting an incident, so whenever an "urgent" appears in the title the incident will automaticaly marked as urgent.

## Update Incident from Incident's Subject

From the **Storyboard**, select the **ProcessorService** and click **Open in Graphical Modeler**.
The CDS Graphical Modeler opens.

Select the **Incidents** entity and click icon **Add Logic**.

![](/exercises/Ex8/images/addapplicationlogic.png)

The **Add Application Logic** dialog box opens.
From the dialog box:

For the **Service Entity** field, make sure that the **ProcessorService.incidents** value is selected.

For the **Name** field, enter **changeUrgencyDueToSubject** for the value.

Click **Add**.

![](/exercises/Ex8/images/applicationlogicdialog.png)

The application logic editor opens.
From the **CONFIGURATION** tab of the application logic editor, select the following options:

In the **Phase** section, select **Before**.

In the **Standard Event** section, select both, **Create** and **Update**.

Click **Open Code Editor > Application Logic**.

![](/exercises/Ex8/images/applicationlogiceditor.png)

The application logic handler file opens.
In the **'changeUrgencyDueToSubject.js'** file, after the comment Your code here, add the following content:

```
const incident = request.data;
if (incident.title?.toLowerCase().includes("urgent")) {
      incident.urgency = {      
        code: "H",        
        descr: "High"        
      };
}
```      

so that you finally see:

![](/exercises/Ex8/images/logiccode.png)

Save the file.

We have now finished configuring the application and we can preview it again.

## Preview the Application

From the left handed activity bar, click icon **Run Configurations**. 

Click the default run configuration: Run incident_managementXXX-1.
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
