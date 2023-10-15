# Exercise 11 - Integrate with SAP Build Work Zone

In the following steps you will add the deployed HTML5 application to a site created in SAP Build Work Zone, standard edition.

## Prerequisite

We already completed in advance the following steps in the SAP BTP cockpit for the relevant subaccount:
- Added an entitlement to SAP Build Work Zone, standard edition.
- Created a subscription to SAP Build Work Zone, standard edition.
- Assigned Launchpad_Admin role collection.

  
## Check the running service and UI after deplyomemnt

Click Start to launch SAP Build Work Zone, standard edition, or open the following URL with your account name:
```
https://lcapteched.dt.launchpad.cfapps.eu10.hana.ondemand.com
```

From the left-side panel, click icon **Channel Manager**
From **HTML5 Apps**, click icon **Update content**.

![](/exercises/Ex11/images/updatecontent.png)

The deployed application is updated in the HTML5 Apps Channel.

From the left-side panel, click icon **Content Manager**.
Click **Content Explorer** and then click the **HTML5 Apps** tile.

![](/exercises/Ex11/images/contentexplorer.png)

Search for the incidentmanagementXXX application where XXX corresponds to your project suffix, and select the checkbox.
Click **Add**.

The application is added to your HTML5 Apps content.

![](/exercises/Ex11/images/addhtmlapp.png)

Go back to **Content Manager**.
Click **Create > Group**.

A New Group editor opens.

In the **Title** field, enter **Incident Management XXX**, where XXX corresponds to your project suffix.
Search for the incidentmanagementXXX app.

Use the toggle in the **Assignment Status** column on the right to assign the application to the group.
Click **Save**.

A group is added to your content.

![](/exercises/Ex11/images/addgroup.png)

Go back to **Content Manager**.
Click the **Everyone** role.
A new editor opens.
Click **Edit**.
Search for the incidentmanagementXXX app, where XXX corresponds to your project suffix.

Use the toggle in the **Assignment Status** column on the right to assign the application to **Everyone**.
Click **Save**.
The application can now be viewed by everyone.

![](/exercises/Ex11/images/everyone.png)

From the left-side panel, click icon **Site Directory**, select **Teched2023** tile.
Click icon **Go to site**.

![](/exercises/Ex11/images/site.png)

Click the **Incident Management XXX** tile, where XXX corresponds to your project suffix.
Your application is launched in a site.

![](/exercises/Ex11/images/appinsite.png)

## Summary

This concludes this hands on.  In just a few chapters without having to code, you have created an OData service based on CAP and a corresponding UI application based on SAP Fiori elements and you have deployed it to SAP's Business Technology Platform. Your application complies to standard designs and comes with a lot of functionality out of the box.

You can continue to an optional exercise to integrate the application to WorkZone - [Exercise 11](../Ex11/README.md)

There are a lot of features of the low code perspective in BAS that we haven't covered in this workshop. So, for completeness let's have a look what you could have also done on top:
- Use authentications for different user roles
    - The service in our project is set up that it can be used for any CRUD operation by users that have a user and password for the corresponding BTP sub-account. However, this is not always what's wanted. While some users might only have read access to our applications others can read and write
    - To support such scenarios one can define authorizations for the service entities and assign different privileges for different user roles. These roles then have to be assigned to users by an administrator after deployment
- Share you project
    - You can enable sharing your project by assigning it to a Git repository
    - You can then not only push your changes to the central Git repo but also allow others to collaborate on the project by sharing the project with them
    - In case of conflicts when several people work on the same project, there are simplified processes to overcome this
- Create a mobile first application with MDK
