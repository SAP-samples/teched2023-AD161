# Exercise 11 [Optional] - Integrate with SAP Build Work Zone

In the following steps you will add the deployed HTML5 application to a site created in SAP Build Work Zone, standard edition.

## Prerequisite

We already completed in advance the following steps in the SAP BTP cockpit for the relevant subaccount:
- Added an entitlement to SAP Build Work Zone, standard edition.
- Created a subscription to SAP Build Work Zone, standard edition.
- Assigned Launchpad_Admin role collection.

  
## Check the running service and UI after deplyomemnt

Click the following URL to launch SAP Build Work Zone, standard edition:

![Work Zone](https://lcapteched.dt.launchpad.cfapps.eu10.hana.ondemand.com)
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

You have integrated your deployed application to Work Zone.
