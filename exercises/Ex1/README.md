# Exercise 1 - Create a Project

In this exercise, we will create incident_management project in the new low-code perspective in the SAP Business Application Studio.

Open your browser and launch the so-called "lobby" using the following URL:
```URL
https://lcapteched-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/lobby
```
You should see the central entry for SAP Build development on SAP BTP.

![](/exercises/Ex1/images/Lobby.png)

Click on the **Create** button and select tile **Build an Application**. 

![](/exercises/Ex1/images/BuildApplication.png)

On the next sreen, select the tile **SAP Build Code**.

![](/exercises/Ex1/images/BuildCode.png)

A dialog appears where you can enter the following name for your project. As we plan to deploy our project it is important to stick to the naming convention here.  

![](/exercises/Ex1/images/FullStack.png)

**DO NOT USE YOUR OWN PROJECT NAME**  

Name your project   
```
incident_managementXXX
```
Where XXX is the user number that was assigned to you. Please make sure that you got a user number assigned by the speakers / moderators, don't make up your own number to avoid clashes with the deployments of others. So if your user number is for example **007** your project name is **incident_management007**

Fill in the fields as shown as below:
1. **Namespace**	teched
2. **Service Name**	Processor
   
You can provide any descriptive text if you want.  
Confirm with a click on **Create**.

From the list of projects, select incident_managementXXX and navigate to the storyboard in SAP Business Application Studio.
![](/exercises/Ex1/images/ProjectLink.png)

After the SAP Business Application Studio has created your environment you should see a screen like this (depending on whether your dev space has already started, this might take several minutes to come up).
![](/exercises/Ex1/images/ProjectCreated.png)

Now we can build our project and use SAP-opinionated technologies such as CAP (Cloud Application Programming Model), Fiori Elements for our purposes without thinking about how to structure our project and being able to concentrate on the tasks to solve rather than spending time to think about project setup and wiring up technologies.

In the next step we will create a data model.

## Summary

You've now created an incident management project with a default Processor service that is ready for modeling based on CAP (Cloud Application Programming model).

Continue to - [Exercise 2](../Ex2/README.md)

