# Exercise 8 - Add Application Logic to the Application
In this excercise we will add a unit test for automatic urgency determination.
The unit test checks that the urgency is raised to high according to the incident’s title.

## Create a Test for Updating the Urgency from an Incident's Title

From the **Application Logic Editor**, select **changeUrgencyDueToSubject** and click **Open Code Editor > Unit Test**.

![](/exercises/Ex9/images/unittestcreate.png)

In the **'test-changeUrgencyDueToSubject.js'** file, after the **Your code here** comment , add the following content:

```
  let draftId, incidentId;

  // Create an incident 
  const createIncident = await POST(`/service/incident_managementXXX/Incidents`, {
    title: 'Urgent attention required!',
  });

  draftId = createIncident.data.ID;
  expect(createIncident.status).to.equal(201);
  expect(createIncident.statusText).to.equal('Created');

  const responseActivate = await POST(
    `/service/incident_managementXXX/Incidents(ID=${draftId},IsActiveEntity=false)/ProcessorService.draftActivate`
  );
  expect(responseActivate.status).to.eql(201);
  incidentId = responseActivate.data.ID;
  // Test the Urgency
  expect(responseActivate.data.urgency_code).to.eql('H');

  const getIncident = await GET(`/service/incident_managementXXX/Incidents(ID=${incidentId},IsActiveEntity=true)`);

  expect(getIncident.status).to.eql(200);
  expect(getIncident.data.urgency_code).to.eql('H');

  // Clean up 
  const responseDelete = await DELETE(`/service/incident_managementXXX/Incidents(ID=${incidentId},IsActiveEntity=true)`);
  expect(responseDelete.status).to.eql(204);
 ```
Save the file.

![](/exercises/Ex9/images/testcode.png)



From the activity bar, click  (Task Explorer).
From the Task Explorer, click  (Create Task).
A dialog box opens.
Select Miscellaneous and then select test.
From the editor that opens, click Run .
The test start running.
Result







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

![](/exercises/Ex8/images/runconfiguration.png)

A preview of the application opens, and the **Incidents** tile is on the on the left-hand side.

Click the **Incidents** tile.
The list of incidents opens in a new tab.

Click the **Strange noise when switching off Inverter incident**, which has **Medium** urgency, and click **Edit**.

Add **Urgent** text to the beginning of the **Title** and click **Save**.

Go back to the list of incidents and see that the **Urgency** changed to **High**.

![](/exercises/Ex8/images/testlogic.png)


## Summary
We have now added application logic to the application. 

Continue to - [Exercise 9](../Ex9/README.md)
