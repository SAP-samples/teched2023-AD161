# Exercise 10 [Optional] - Add Unit Tests to the Application
In this excercise we will add a unit test for automatic urgency determination.
The unit test checks that the urgency is raised to **high** according to the incident’s title.

## Create a Test for Updating the Urgency from an Incident's Title

From the **Application Logic Editor**, select **changeUrgencyDueToSubject**, and then click **Open Code Editor > Unit Test**.

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
Replace  **XXX** in the 4 placeholders in the copied code with your project's suffix.

Save the file.

![](/exercises/Ex9/images/testcode.png)

Now we will run the the test from the terminal.

From the activity bar, select the hamburger icon, and then choose **Terminal > New Terminal**.

![](/exercises/Ex9/images/terminal.png)

The Terminal opens. 
Copy the following command, paste it in the terminal, and press **Enter** to run the test.

```
basctl --command lcap.applicationLogic.runTest
```

![](/exercises/Ex9/images/rununittests.png)

The test starts running, and the following **PASS** indication should be dispalyed in the terminal:

![](/exercises/Ex9/images/testpass.png)


## Summary
We have now added a unit test to the application. 

Continue to - [Exercise 11](../Ex11/README.md)
