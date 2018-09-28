---
summary: Follow this tutorial to quickly create and test an example mobile app to manage tasks.
tags: runtime-mobile; support-Mobile_Apps; support-Mobile_Apps-overview
---

# Create Your First Mobile App

Developing mobile apps with OutSystems is easy. If you have an Excel file containing your data, you can import it into a database and quickly create a mobile app that enables you to consult and manage your data on the go.

To create a mobile app with data that's imported from an Excel file, you need to:

  1. Create a database model, and import the data from the Excel file into the database;
  2. Create a screen that lists the data from the database;
  3. Create a screen that enables you to create new records, and update existing ones;
  4. Implement functionality to delete records from the database;
  5. Test the application on your mobile device.



Let's do this! In this example we'll use a sample Excel file with to-do task information, and we'll create a simple task management mobile app.


## Create a Mobile App

Let's create a new task management mobile app. An application contains one or more modules, different parts of the application can be encapsulated in a module. A module is where you design the data model, implement the logic, and design the UI of your application.

In the Development Environment, using the Phone template, create a new mobile app called ToDo, and then create a new module for the application.

![Create a Mobile App](images/create-mobile.png)


## Create a Database Table from an Excel File

OutSystems stores your application data in a relational database. This means that the first step in creating an application is defining the data model.

To do this, we are going to use an Excel file that already contains the following task information:

  * Description;
  * Due Date;
  * Is Active.

In the Development Environment, open the Data tab on the top right-hand corner, right-click the Entities folder, choose 'Import Entities from Excel...', and select the sample file `Todos.xlsx` available by default in the directory `C:\Program Files\OutSystems\Development Environment 11.0\Service Studio\TutorialResources`.

![Create a Database Table from an Excel File](images/create-mobile-db-table-excel.png)

When importing an Excel file, OutSystems creates a database table (called an Entity in OutSystems) with the necessary columns (called Attributes in OutSystems) to store the data in the database.

Behind the scenes, OutSystems also creates logic to import each row in the Excel file into a corresponding database record. After publishing your application, the background logic populates your database with the data from the Excel file.

In this tutorial we're only storing the data in the server database, but for offline usage, it's also possible to store the data locally in mobile devices using Local Storage.


## Create a Screen to List Tasks

Now that we have our to-do tasks stored on the database, we can create a screen that lists all of the tasks.

Drag and drop the entity Todo from the Data tab to the Content placeholder of the mobile screen that is displayed in the Main Editor window.

![Create a Screen to List Tasks](images/create-mobile-list.png)

This updates the HomeScreen to include a list that initially displays 20 tasks and automatically loads more tasks when the user scrolls to the end of the list.

![Tasks Screen](images/create-mobile-screen.png)


## Create a Screen to Edit Tasks

Creating a screen to edit the records is as fast as creating a list screen.

Right-click the title of the first task in the list and choose **Link to ![Mobile Screen](../shared/icons-service-studio/screen-mobile.png) (New Screen)**.

![Create a Screen to Edit Tasks](images/create-mobile-edit-1.png)

This links the title of the tasks to a newly created screen. We will use this new screen to edit the tasks, but for that we will need a form:

1. Drag and drop a Form widget from the toolbox to the empty area in the new mobile screen;
2. Drag and drop the entity Todo from the Data tab to the previously created Form widget.

![Create a Screen to Edit Tasks](images/create-mobile-edit-2.png)

Now we will define the logic that runs when the end users press the Save button:

1. Double-click an empty area of the button Save to define the logic associated with the button. This will create a new screen action named **SaveOnClick**;
2. Drag and drop the entity action **CreateOrUpdateTodo**, available under the entity Todo tree, to the True branch of the If in the **SaveOnClick** action. Set the property Source to `GetTodoById.List.Current`.
3. Drag and drop the screen HomeScreen from the Interface tab to the End node so that the user is redirected back to the main screen after saving a task.  

![Create a Screen to Edit Tasks](images/create-mobile-edit-3.png)


## Allow Adding Tasks

We want to enable the end users to add new tasks from the list screen by linking to the screen that is already used to edit tasks:

1. Double-click the HomeScreen in the tree of the Interface tab to open the list screen;
2. Drag and drop an Icon widget from the toolbox to the Actions placeholder in the top right-hand corner of the screen and select the icon plus;
3. Right-click the icon and choose **Link to ![Mobile Screen](../shared/icons-service-studio/screen-mobile.png) MainFlow\Todo**.  

![Allow Adding Tasks](images/create-mobile-add.png)


## Allow Completing Tasks

Now let's add the functionality to mark tasks as complete. Let's implement that by deleting the completed tasks:

1. Select an item of the list and then click Swipe Left Action on the toolbar;
2. Replace the text "Action" with "Done";  
![Allow Completing Tasks](images/create-mobile-complete-1.png)
3. Double-click an empty area of the Swipe Left area to define the logic associated with the Swipe Left Action;
4. Drag and drop the entity action **DeleteTodo** available under the entity Todo in the Data tab to the flow of the Swipe Left Action. Set the property Id to `GetTodos.List.Current.Todo.Id`;
5. Drag and drop the Refresh Data tool to the flow of the action and select the aggregate GetTodos to refresh the available tasks in the screen.  
![Allow Completing Tasks](images/create-mobile-complete-2.png)


## Test Your Mobile App

At this stage we test the mobile app. Click the ![1-Click Publish](../shared/icons-service-studio/publish.png) 1-Click Publish button to publish the application to your environment.

![Publish Your Mobile App](images/create-mobile-publish.png)

When the application is deployed, click the ![Open in Browser](../shared/icons-service-studio/open-browser.png) Open in Browser button to test your application in a browser (Chrome and Safari are supported).

To test the application on your mobile device see [Preview Your Mobile App in the Device Using OutSystems Now](../deliver-mobile/preview-your-mobile-app-in-the-device-using-outsystems-now.md).

