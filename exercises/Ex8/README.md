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

From the **Run Configurations** view, click icon **Run Module**.


## Summary
We have now added application logic to the application. We have learned that using the low code tools, one can switch to normal textual editors to change / add code.

Continue to - [Exercise 7](../ex7/README.md)
