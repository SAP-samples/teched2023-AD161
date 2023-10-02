# Exercise 6 - Add Application Logic to the Application

## The additional Scenario

While we already have a running CRUD application, we want to improve it now.
We would like to get a visual hint that the criticality of a request is high depending on the total cost of the request. This should be shown in the list of Capex requirements like this:

![](/exercises/ex6/images/LCAP_60.png)

In order to do achieve this, we need to do several things, most prominently to add some application logic to the project.

## The Code behind the Scenes

To create the project up to this point you have not seen any code, everything was built using visual editors. However, under the hood code is created using the technologies that are part of the low code perspective of the Business Application Studio. In this project it is CAP and Fiori elements. There is also the Mobile Development Kit (MDK) that is not covered in this hands on.

For all these technologies whenever you change something in the visual editors, the code is created. The code that is created is very much the code that a developer could have written using just the text editors. There is **no additional or different metatdata** created.

In fact you can see the code. And what's more you can decide at any point in the project that from now on you'd rather carry on with textual editors adding more code / changing the generated code. With this is becomes possible not only to use the low code tools to create complete applications but also to jump start any kind of development that involves CAP, Fiori elements or MDK. You can use the visual tools to a certain point of your liking, where you think the tools support what you want to do in an optimal way and then switch to the code. Get the straight forward things done really easily and fast and if the editors do not provide enough functionality to do the final 20% of the resulting applications, one can switch to the code editors and finish it there.

How do switch to the code? Let's do this now.

Press the button in the left sidebar at the very top, then choose **View** and **Explorer** as entries

![](/exercises/ex6/images/LCAP_61.png)

Now a new side pane opens at the left and it contains the file structure of our project. You can see a **db** and a **srv** folder there, both are standard CAP folders that hold the data models and the services respectively. There is also the **app** folder which holds our Fiori elements UI application, if there are more than one and additional MDK applications you can also find them in this folder.

![](/exercises/ex6/images/LCAP_62.png)

Let's open the file **schema.cds** in the **db** folder. You can now see a text file which reflects the data models for Capex and Category that we have created using the graphical modeler. This is code in the Core Data Service (CDS) format and you could now edit it and enhance it. For CDS files this even works in both directions. You can either change the CDS file and the change is reflected in the graphical modeler and vice versa. Being able to edit in both direction doesn't work for all file types (e.g. not for Javascript files) but as a general rule you can always at any point leave the graphical editors, switch to the file structure and from then on code in text editors.

## Add a new Property to the Data Model

In order to control the crtiticality of a Capex registration entry on the UI, we need a new property. To get it, on the **Home** page, under **Data Models** press on the **Capex** entry. In the Data Modeler, by pressing on the header area of the **Capex** entity, bring up the menu and press the pencil like icon to be able to add the properties of the entity. Add a property called **criticality** of type **Integer** to the data model:

![](/exercises/ex6/images/LCAP_63.png)

Press **Update** to save the change. The property is now added to the data model and because our **Capex** service entity also projects from the **Capex** data model 1:1 it is also automatically part of the service entity.

Note, we have added the new property to our data base. As the property is only needed to control the UI and as you will see in a later step is calculated at runtime, there is really no need to add it to the data base. There are also options to add it as a calculation field to a service only, but for simplicity reasons we still add it to the data base.



## Add an Application Logic Handler to the project

Now we need to add the logic part. 
For this, on the **Home** page, in the **Service** tile choose the **Capex**  again. On the graphical modeler, invoke the menu by clicking on the header of **Capex** and select the **Add Logic** command.

![](/exercises/ex6/images/LCAP_64.png)

Now there will be a dialog for you to enter a service entity (which we already have chosen, it is the **Capex** one) and a name for the new handler. The one that the system suggests is fine, take it all over by pressing the **Add** button:

![](/exercises/ex6/images/LCAP_64-2.png)

One the following screen you can specify when the new handler should be invoked. Ours should be invoked **After** there was a **Read** request for the **Capex** entity. Select these properties and then press the **Open JS Editor** button:

![](/exercises/ex6/images/LCAP_64-3.png)

Now a new text file is opened. It already contains the stub for our handler function. Replace the line:

```Javascript
    // Your code here
```

with:

```Javascript
    const capexs = Array.isArray(context.results) ? context.results : [context.results];
    capexs.forEach(capex => {
        if (capex.totalcost > 200) {
            capex.criticality = 1;
        } else {
            capex.criticality = 2;
        }
    });
```

so that you finally see:

![](/exercises/ex6/images/LCAP_65.png)

Save the file.

Let's have a look what happens in the code. As set up, the function is invoked after the was a read request for the **Capex** entity. The request could for example be created as an OData GET request from the browser. The CAP framework invokes our custom handler and passes the data into it, that it has just retrieved from the data base. It might be one or more entities. Our code looks into the data, it looks whether **totalcost** is greater than 200, if so, it sets our new **criticality** property to 1 otherwise to 2.

So, with this, the criticality is set according to the total cost of our Capex express.

## Adjust the UI based on the Application Logic

We now need to adjust our UI application making use of the values in Capex's **criticality** property. We are going to use the **totalcost** field on the UI to change its look depending on the value of the criticality.

To do this, switch back to the **Home** tab. Under **User Interfaces**, click on your **My List Report** application. The **Page Map** opens, for the **List Report** page, invoke the pencil shaped icon to configure the page. Expand the **Table** and then the **Columns** entry and select the **totalcost** property.

Look for the **Criticality** box under the properties of **totalcost**. We can use it to display the criticality of the totalcost. If you expand the dropdown here, you find a list of the property of the **Capex** entity. Choose the criticality one. Note, the criticality functionality is called like we have called our service entity's property, but we could have chosen any other name for the property as well.

![](/exercises/ex6/images/LCAP_66.png)

After a couple of seconds after you have selected the **critiality** property, a new **Criticality Representation** box appears. Here we can configure how the criticality is visually represented, with just a color, with an addition icon or not at all. In our case, we want to add an icon as well to a color change, so choose the **With Icon** entry

![](/exercises/ex6/images/LCAP_67.png)

## Preview the Application

We have now finished configuring the application and we can preview it again.

Go back to the **Home** tab and on the **Preview** button in the upper right part of the screen, select **With Live Data**. As before after a couple of seconds the **Project Preview** page comes up. Click on the **My List Report** application again. It should come up as before. Click on its **Create** button above the empty list.

Fill out the form, pick any *BusinessPartner** from the value help and any **Category** from the dropdown and fill in a **description** of your choice. Make sure that for this first request you choose a value for **totalcost** which is *smaller* than the threshold in our application handler code, so smaller than **200**

![](/exercises/ex6/images/LCAP_68.png)

Press the **Create** button at the bottom of the page to save the data. Then press the **<** button in the top left part of the screen to return to the list page. Here press the **Go** button and your new entry should appear in the list. Not how the text in the **totalcost** column is now yellow and has a warning icon with it, indicating a criticality of lower priority.

![](/exercises/ex6/images/LCAP_69.png)

Now press **Create** again to add a second entry. This time make sure that you choose a value that is **greater** than 200. After you have saved the entry and returned to the list page you should see the new entry also, colored in red and with an appropriate icon, indicating the highest criticality:

![](/exercises/ex6/images/LCAP_60.png)

## Summary
We have now added application logic to the application. We have learned that using the low code tools, one can switch to normal textual editors to change / add code.

Continue to - [Exercise 7](../ex7/README.md)
