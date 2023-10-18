# Exercise 8 - Add Application Logic to the Application
In this exercise, we will add a logic of automatic urgency determination.
Customers may forget to select the urgency when creating an incident, so whenever an "Urgent" appears in the title, the incident will automatically be marked as urgent.

## Update Incident from the Incident's Subject

From the **Storyboard**, select the **ProcessorService**, and click **Open in Graphical Modeler**.
The CDS Graphical Modeler opens.

Select the **Incidents** entity and click the **Add Logic** icon.

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

In the **Standard Event** section, select **Create** and **Update**.

Click **Open Code Editor > Application Logic**.

![](/exercises/Ex8/images/applicationlogiceditor.png)

The application logic handler file opens.
In the **'changeUrgencyDueToSubject.js'** file, after the comment "//Your code here", add the following content:

```
const incident = request.data;
if (incident.title?.toLowerCase().includes("urgent")) {
      incident.urgency = {      
        code: "H",        
        descr: "High"        
      };
}
```      

The outcome should look like this:

![](/exercises/Ex8/images/logiccode.png)

Save the file.

We have now finished configuring the application and we can preview it.

## Preview the Application

From the activity bar on the left of the page, click the **Run Configurations** icon. 

From the **Run Configurations** view, click the **Run Module** icon.

![](/exercises/Ex8/images/runconfiguration.png)

A preview of the application opens, showing the **Incidents** tile on the left.

Click the **Incidents** tile.
The list of incidents opens in a new tab.

Click the **Strange noise when switching off Inverter incident**, which has **Medium** urgency, and then click **Edit**.

Add the word **Urgent** to the beginning of the **Title** and click **Save**.

Go back to the list of incidents and see that the **Urgency** changed to **High**.

![](/exercises/Ex8/images/testlogic.png)


## Summary
We added application logic to the application. 

Continue to - [Exercise 9](../Ex10/README.md)
