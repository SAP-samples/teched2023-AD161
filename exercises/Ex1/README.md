# Exercise 1 - Create a project

In this exercise, we will create incident_management project in the new low-code perspective in the SAP Business Application Studio.

3.2.	From the landing page, click Create and select Build an Application.
4.	Select the SAP Build Code tile and then the Full-Stack Application tile.
5.	Fill in the fields as shown in the table below:
Property	Value
Project Name	incident_management
Description	Incident Management Application
Namespace	sap.capire.incidents
Service Name	ProcessorService
Dev Space	Full Stack Cloud Application
6.	Click Create.
7.	From the list of projects, select incident_management and navigate to the storyboard in SAP Business Application Studio.


Open your browser and launch the so-called "lobby" using the following URL:
```URL
https://lcapteched-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/lobby
```
You should see the central entry for low-code / no-code development on SAP BTP.

![](/exercises/ex1/images/lobby_01.png)

Click on the "Create" button and select tile "Build an Application". 

![](/exercises/Ex1/images/BuildApplication.png)

On the next sreen, select the tile "SAP Build Code".

![](/exercises/Ex1/images/BuildCode.png)

![](/exercises/ex1/images/lobby_03.png)

A dialog appears where you can enter the following name for your project. As we plan to deploy our project it is important to stick to the naming convention here.  

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



After the SAP Business Application Studio has created your environment you should see a screen like this (depending on whether your dev space has already started, this might take several minutes to come up). Make sure you select the **Home** tab (you might see **Guided Development** first):
![](/exercises/ex1/images/LCAP_01.png)

Now we can build our project and use SAP-opinionated technologies such as CAP (Cloud Application Programming Model), Fiori Elements and MDK (Mobile Development Kit) for our purposes without thinking about how to structure our project and being able to concentrate on the tasks to solve rather than spending time to think about project setup and wiring up technologies.

In the next step we will create a data model.

## Summary

You've now created a data model including persistence in CAP (Cloud Application Programming model) that can be later used to be deployed to the SAP HANA database we will use. Note that you have not seen any CAP related commands or syntax.

Continue to - [Exercise 1.5](../ex1.5/README.md)

