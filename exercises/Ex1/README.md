# Exercise 1 - Create a Project

In this exercise, we will create an incident_management project in the new low-code perspective in SAP Business Application Studio.

Open your browser and launch the landing page, the "lobby", using the following URL:
```URL
https://lcapteched-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/lobby
```
A login page is opened, enter the credentials provided to you for the session.

You should see the central entry point for SAP Build development in SAP BTP.

The "lobby"may already contain multiple projects created in this account.

![](/exercises/Ex1/images/Lobby.png)

Click the **Create** button and select the **Build an Application** tile. 

!![](/exercises/Ex1/images/BuildApplication.png)

On the next screen, select the **SAP Build Code** tile.

![](/exercises/Ex1/images/BuildCode.png)

A dialog appears where you can enter the following name for your project. As we plan to deploy our project, it is important to stick to the naming convention here.  


**DO NOT USE YOUR OWN PROJECT NAME**  

Name your project   
```
incident_managementXXX
```
Where XXX is the user number that was assigned to you. Please make sure that you recieved a user number that was assigned to you by the speakers / moderators. Don't make up your own number to avoid clashes with the deployments of others. If your user number is **007** your project name should be **incident_management007**

Fill in the fields as shown below:
1. **Namespace**	teched
2. **Service Name**	Processor
   
You can provide any descriptive text that you want.  
Confirm by clicking **Create**. 

The project creation may last 2-3 minutes.

![](/exercises/Ex1/images/FullStack.png)

From the list of projects, select incident_managementXXX and navigate to the storyboard in SAP Business Application Studio.
![](/exercises/Ex1/images/ProjectLink.png)

After SAP Business Application Studio has created your environment, you should see a screen like this. (Depending on whether your dev space has already started, this might take several minutes to open.)

![](/exercises/Ex1/images/ProjectCreated.png)

Now, we can build our project and use SAP-opinionated technologies, such as CAP (Cloud Application Programming Model) and SAP Fiori elements, without thinking about how to structure our project. We can concentrate on the tasks to perform rather than spending time on thinking about project setup and wiring up technologies.

In the next step, we will create a data model.

## Summary

You've now created an incident management project with a default Processor service that is ready for modeling, based on CAP (Cloud Application Programming model).

Continue to [Exercise 2](../Ex2/README.md).

