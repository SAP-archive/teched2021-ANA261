# Exercise 1


## Estimated Time: xx minutes

## Objective

In this exercise, you will build your first new model in SAP Analytics Cloud.  You will create this model from scratch, using a structure first modeling workflow.  


## What You Learn

*Model configuration

*Adding dimensions and measures

*Using public dimensions

*Managing local dimensions



### Step 1


Open the url provided in the requirements section and log in, using one of the studentXX logins and the password, also from the requirements section.

![][image-1]
### Step 2


If this is the first logon for this user, you will see this GDPR greeting popup.  Click Accept to continue.

If this user has already been used to log in, you will not see this popup.

![][image-2]
### Step 3


If this is the first logon for this user, you will see this GDPR greeting popup.  Click Accept to continue.

If this user has already been used to log in, you will not see this popup.

![][image-3]
### Step 4


From the navigation strip, at the left edge of the screen, click on Modeler.  This will take you to the modeling module.

![][image-4]
### Step 5


In the Modeler, you have four options for creating a model.  In this exercise, we will be creating a New Model from scratch, so choose the leftmost button, “Create a new model”.  Creating a model from scratch is known as “Structure First” modeling.  Creating a model from an uploaded file for data from a connection is known as “Data First” modeling.

![][image-5]
### Step 6


You will see a popup, allowing you to choose between the classic account model and the new model.  New model is the default and the recommended model type when you are creating a model in a structure first workflow.

![][image-6]
### Step 7


Take a moment to orient yourself in the structure first modeling environment.  In the panel on the left-hand side, you see an overview of the measures and dimensions in the model.  In the center, you see the structure.  On the right, you see model details.  If you select an individual measure or dimension on the left side, this will show the dimension/member specific details.

![][image-7]
### Step 8


Let’s add our first dimension.  Start by clicking on the pulldown arrow, on the Dimensions section of the left panel.

![][image-8]
### Step 9


This dimension will be a public dimension, which has already been maintained.  So choose “Add existing dimensions”.

![][image-9]
### Step 10


Next, choose “Generic”.

![][image-10]
### Step 11


The dimension that we want to add is State, which contains US states and territories.  Since there are many public dimensions on this tenant, you might want to use the search feature.  Type in “st” and click the magnifying lens.  

![][image-11]
### Step 12


Select State and click Add.  Note how the model diagram changes.  Alternatively, you can select StateWithRegion, which is the same list of states and territories, but with a parent child hierarchy.  The rest of this exercise presumes that you went with the 

![][image-12]
### Step 13


Use the same method to add two additional public dimensions; Region and NationalPark.

![][image-13]
### Step 14


Let’s add a local dimension, which will only exist inside this model.  Start by clicking on the pulldown arrow, on the Dimensions section of the left panel.  Select “Add new Dimension”.

![][image-14]
### Step 15


Call your dimension “UnitType”.

![][image-15]
### Step 16


Click on the text of your new dimension, to view and edit its members.  In the menu bar, click the Plus sign, to add a member.  

![][image-16]
### Step 17


Call this member “National Monument”.

![][image-17]
### Step 18


This is the list view.  There is an alternative, spreadsheet style view, which might be more comfortable when maintaining many dimensions.  To go to this view, click the grid icon, to toggle into grid view.

![][image-18]
### Step 19


In grid view, you can simply click on a new row and directly edit the ID and description of a member.  Add “National Park” to the Member ID in the first empty row.

![][image-19]
### Step 20


After hitting Enter, you have three dimension members.

![][image-20]
### Step 21


Click the back arrow, to return to the model.

![][image-21]
### Step 22


Now we will begin adding measure.  Slick the Add button in the Measures area.

![][image-22]
### Step 23


Set the name of the measure to RecreationVisits.

![][image-23]
### Step 24


Set the description to “Daytrip Visitors”.  Set the data type to Integer.

![][image-24]
### Step 25


Add the rest of the measures:

ConcessionerLodging
ConcessionerCamping
TentCampers
RVCampers
Backcountry

![][image-25]
### Step 26


Click to save the model

![][image-26]
### Step 27


Name the model NationalParkVisitation.  Make sure to save this in your My Files folder and not in Public.  There will be dozens of other people creating models in this session.  If you do want to save it to Public for some reason, add a “_XX” suffix to the name, where the XX is the student number that you logged on with.

![][image-27]
### Step 28


This is how your model should now look.  It won’t contain any data yet.  You’ll change that in the next exercise.

![][image-28]
### Step 29




![][image-29]


## Summary

You created a model for analyzing visitation at National Parks in the United States.  Congratulations, you have learned the first basics of building a model structure.































[image-1]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.01.png
[image-2]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.02.png
[image-3]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.03.png
[image-4]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.04.png
[image-5]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.05.png
[image-6]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.06.png
[image-7]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.07.png
[image-8]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.08.png
[image-9]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.09.png
[image-10]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.10.png
[image-11]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.11.png
[image-12]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.12.png
[image-13]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.13.png
[image-14]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.14.png
[image-15]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.15.png
[image-16]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.16.png
[image-17]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.17.png
[image-18]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.18.png
[image-19]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.19.png
[image-20]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.20.png
[image-21]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.21.png
[image-22]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.22.png
[image-23]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.23.png
[image-24]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.24.png
[image-25]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.25.png
[image-26]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.26.png
[image-27]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.27.png
[image-28]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.28.png
[image-29]:    https://github.com/SAP-samples/teched2021-ANA261-ANA261/raw/main/exercises/ex1/images/Ex1.29.png

