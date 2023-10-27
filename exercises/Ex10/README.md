# Exercise 9 - Deploy Your Application

In this section, we will deploy the project to the Business Technology Platform (BTP), Cloud Foundry environment.

## Deploy the project to BTP

We already completed the environment set up for you. This is what we did:

* Enabled the Cloud Foundry environment.
   
* Added an entitlement for SAP HANA Cloud.
   
* Added an entitlement for SAP HANA Schemas & HDI Containers.
   
* Added you as a member in a Cloud Foundry space.
   
Since these steps are completed, you can now select a space and deploy an application to the SAP BTP, Cloud Foundry environment.

Deployment is composed of 3 steps that are available from the **Task Explorer**:

1. Build an application.
   
2. Log in to the target space in the Cloud Foundry environment.
   
3. Deploy the application.
   
To start deployment:<br>

From the activity bar, click the **Task Explorer** icon.

Expand the **Deploy** section, select **Deploy incident_managementXXX**, and then click the **Run** icon.

![](/exercises/Ex10/images/deployconfiguration.png)  

A build starts and the **Cloud Foundry Sign In and Targets editor** opens.

- Enter the following Cloud Foundry endpoint **https://api.cf.eu10-004.hana.ondemand.com** .<br>
  **Important**: Sometimes, the system recommends the **https://api.cf.eu10.hana.ondemand.com** URL. Make sure you manually enter the **-004** part behind **eu10**.<br>

- Choose **SSO Passcode** as the authentication method.<br>

- Press the **Open a new browser page to generate your SSO passcode** link.<be>

![](/exercises/Ex10/images/logincf.png)  

- Next, provide the value 'lcap-platform' and choose 'Sign in with Alternative Identity Provider'
![](/exercises/Ex10/images/GetSSO.png)  

This opens a new page, with a temporary passcode created for your user.

- Press the button on the right of the password to copy it to the clipboard as indicated here:

![](/exercises/Ex10/images/passcode.png)  

- Paste the copied passcode into the field **Enter your SSO Passcode** on the **Cloud Foundry Sign In and Targets editor** page.
- Click **Sign In**.

After a couple of seconds, the following page opens:

![](/exercises/Ex10/images/spaceselection.png)  

In this page:

- Choose the **TechEdLCAP_lcapteched** organization.
- Choose the **dev** space.
- Click **Apply**.

The deployment starts and progress can be tracked in the Terminal.
It takes **several minutes** for the application to be deployed.

## Check the running service and UI after deployment

Once Deploy is complete, copy or click on the URL that appears at the end of the Terminal logs under **Project OverviewURL**.<br>
For example, **https://<myaccount>.launchpad.cfapps.<myregion>.hana.ondemand.com/lcapincident_managementXXX.incident_managementLaunchpad-1.0.0**

![](/exercises/Ex10/images/linktoapp.png)

Click the **Incidents** tile to open the application with a list of incidents.

It looks very much like the preview page from the last chapter. Indeed, it is almost the same page, but now everything is deployed and runs in the BTP account. <br>


## Summary

This concludes this hands-on. In just a few chapters, and without writing code, you have created an OData service based on CAP and a corresponding UI application based on SAP Fiori elements, which you then deployed to the SAP Business Technology Platform. Your application complies to standard designs and comes with a lot of functionality out-of-the-box.

You can continue to optional exercises to add unit tests and integrate the application to SAP Build Work Zone - [Exercise 10](../Ex9/README.md)

High productivity tools in BAS have many more capabilities that were not covered in this workshop. So, for the sake of completeness, let's have a look what else you could have done:
- Use authentications for different user roles
    - The service in our project is set up so that it can be used for any CRUD operation by users that have a user and password for the corresponding BTP sub-account. However, this is not always what you want. While some users might only have read access to our applications, others can read and write.
    - To support such scenarios, one can define authorizations for the service entities and assign different privileges for the different user roles. These roles then have to be assigned to users by an administrator after deployment.
- Share you project.
    - You can enable project sharing by assigning it to a Git repository.
    - You can then not only push your changes to the central Git repository, but you can also allow others to collaborate on the project by sharing the project with them.
    - In case of conflicts when several people work on the same project, there are simplified processes to overcome this.
- Create a mobile first application with MDK.
- Integrate your project with CI-CD using the SAP Continuous Integration and Delivery service.

