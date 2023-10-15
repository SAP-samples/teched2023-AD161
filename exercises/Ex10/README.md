# Exercise 10 - Deploy your service and application

In this section we will deploy the project to the Business Technology Platform (BTP) Cloud Foundry environment.

## Deploy the project to BTP

We already completed the environment set up:

1. Enabled the Cloud Foundry environment.
   
3. Added an entitlement for SAP HANA Cloud.
   
5. Added an entitlement for SAP HANA Schemas & HDI Containers.
   
7. Added you as a member in a Cloud Foundry space.
   
Since these steps are completed, you will be able to select a space and deploy an application in the SAP BTP, Cloud Foundry environment.

The deployment is composed of 3 steps that are available from the **Task Explorer**:

1. Build an application.
   
3. Log in to the target space in the Cloud Foundry environment.
   
3. Deploy the application.
   
To start the deployment, perform the following steps:
From the activity bar, click icon **Task Explorer**.

Expand the **Deploy** section, select **Deploy incident_managementXXX**, and click icon **Run**.

![](/exercises/Ex10/images/deployconfiguration.png)  

A build starts and then the **Cloud Foundry Sign In and Targets editor** opens.

- The Cloud Foundry Endpoint **https://api.cf.eu10-004.hana.ondemand.com** .
  **Note**: that the system recommends the URL https://api.cf.eu10.hana.ondemand.com make sure you manually enter the **-004** part behind **eu10** !

- Choose **SSO Passcode** as the authentication method

- Press the link **Open a new browser page to generate your SSO passcode**

![](/exercises/Ex10/images/logincf.png)  

This opens a new page, with a temporary passcode created for you user.

- Press the button right to it in order to copy the passcode to the clipboard as indicated here:

![](/exercises/Ex10/images/passcode.png)  

- Paste the copied passcode into the field **Enter your SSO Passcode** back on the screen before.
- Press **Sign In**

After a couple of seconds a new screen opens like this:

![](/exercises/Ex10/images/spaceselection.png)  

Here:

- Choose the organization **TechEdLCAP_lcapteched**
- Choose the space **dev**
- Press **Apply**

The deployment starts and progress can be tracked in the Terminal.
It will now take several minutes for the application to be deployed.

## Check the running service and UI after deplyomemnt

Once Deploy is complete, copy or click on the URL that appears at the end of the Terminal logs under **Project OverviewURL**.
For example, https://<myaccount>.launchpad.cfapps.<myregion>.hana.ondemand.com/lcapincident_managementXXX.incident_managementLaunchpad-1.0.0

![](/exercises/Ex10/images/linktoapp.png)

Click the **Incidents** tile to open the application with a list of incidents.

It looks very much like the preview page from last chapter. Indeed it is almost the same page, only that now everything is deployed to a an account in the BTP. Again you can click on the service links on the right and / or the UI application.

## Summary

This concludes this hands on. In just a few chapters without having to code, you have created an OData service based on CAP and a corresponding UI application based on SAP Fiori elements and you have deployed it to SAP's Business Technology Platform. Your application complies to standard designs and comes with a lot of functionality out of the box.

There are a lot of features of the low code perspective in BAS that we haven't covered in this workshop. So, for completeness let's have a look what you could have also done on top:
- Use authentications for different user roles
    - The service in our project is set up that it can be used for any CRUD operation by users that have a user and password for the corresponding BTP sub-account. However, this is not always what's wanted. While some users might only have read access to our applications others can read and write
    - To support such scenarios one can define authorizations for the service entities and assign different privileges for different user roles. These roles then have to be assigned to users by an administrator after deployment
- Share you project
    - You can enable sharing your project by assigning it to a Git repository
    - You can then not only push your changes to the central Git repo but also allow others to collaborate on the project by sharing the project with them
    - In case of conflicts when several people work on the same project, there are simplified processes to overcome this
- Create a mobile first application with MDK
- Integrate your project with CI-CD using the BTP continuous integration service

