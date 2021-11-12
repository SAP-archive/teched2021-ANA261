# Exercise 3


## Estimated Time: 30 minutes

## Objective

Your load job from [Exercise 2](https://github.com/SAP-samples/teched2021-ANA261/tree/main/exercises/ex2) has rejected rows.  In this exercise, you will fix the problem preventing a clean import job in [Exercise 2](https://github.com/SAP-samples/teched2021-ANA261/tree/main/exercises/ex2).  We’ll have a look at the cause of these errors, fix them and execute the load.  You will do this by modifying the model itself.  Additionally, you’ll modify the import wrangling job, before re-executing the import.  


## What You Learn

* Removing and adding dimensions from after data has been loaded

* Modifying and re-executing import jobs.



### Step 1


Your starting point is in the Model Structure view, where you left off in [Exercise 2](https://github.com/SAP-samples/teched2021-ANA261/tree/main/exercises/ex2).  Navigate to the Data Management view.

![][image-1]
### Step 2


In the Import History pane, look at the load job summary.  Click on the link “Rejection Summary”, to download a CSV file with all of the rejection information.

![][image-2]
### Step 3


There are four rows in the rejection summary.  Each refers to an error “Member does not exist”.  This error is happening because there are unmaintained dimension member values.  

The data is being loaded into the data foundation, also called a fact table.  Your model is in a star schema, and the language of SQL, the dimensions columns all have a [foreign key constraint](https://www.w3schools.com/sql/sql_foreignkey.asp), with the primary key being in the dimension definition table.  Since there is no corresponding primary key, these values can’t be loaded.

The option to automatically update the dimension metadata will be added, but is not in place yet, so you will have to edit the metadata to fix the problem.

![][image-3]
### Step 4


The simplest option would simply be to add the missing values to the Member ID columns of the UnitType dimension and re-execute the load job.  We won’t do this, because we’ll use this opportunity to show you what happens when you modify the structure of a model after loading data.  

Go back to the Model Structure view.  To delete the UnitType dimension.  Click on the garbage can ion, on the hover menu of the UnitType.

![][image-4]
### Step 5


SAP Analytics Cloud will now warn you about how this will affect your data.  If there are records in the data foundation, which were distinguished form each other only by this dimension, then they’ll be aggregated (e.g. all relevant measure values will be summed up) 

![][image-5]
### Step 6


There is an existing Public dimension. Which already has all these dimension members maintained.  We’ll use this, so select the button to add a dimensions and select “Add existing dimensions”

![][image-6]
### Step 7


Select a Generic type and click Add.

![][image-7]
### Step 8


The dimension is called NationalParkUnitType.  This tenant has a large number of dimensions, so you an find it quickly by searching for the text “National”.  Select it and click add.

![][image-8]
### Step 9


Click to save your model.  

![][image-9]
### Step 10


Don’t panic when you see this popup.  The values can’t be empty, so we need to choose a default value.  That’s what this popup is all about.

![][image-10]
### Step 11


Click on the member input and select any value from the dropdown, ideally unassigned.  Lick on Ok to confirm.

![][image-11]
### Step 12


Click Ok to lose this dialog and save your model changes.  

![][image-12]
### Step 13


You have added a dimension to your model and filled it with dummy data.  To make this dimension useful, you will need to import valid data into it.

Important!  Steps 13 to 15 are OPTIONAL!  You do not need to empty your fact table.  Re-running the import job will update the records where the import dataset and the fact data differ.  Because there are no “unassigned” values in the import data, every record will be updated.  If you want to learn how to clear a fact table, go ahead and proceed through the next three steps.

You can clear the data foundation by selecting the Delete Fats icon. In the Data area of the toolbar.

![][image-13]
### Step 14


In the following dialog, you select which version you want to clear the fact table for.  Planning models can have multiple fact tables, called versions, and you need to clarify which one you want to clear.  Analytic models only have an Actual version.  

![][image-14]
### Step 15


Confirm that you want to clear the Data Foundation (Fact table)

![][image-15]
### Step 16


Navigate to the Data Management view.  At the far-right end of the import job listing, there is an ellipsis icon.  Select it and from the popup menu, choose Edit.  

![][image-16]
### Step 17


You are back in the wrangler step of the import job workflow.  Navigate to the transform log.  

Recall that the transformations execute in sequence, from top to bottom.  We are going to add a transformation that will clean up the data quality of some of the unmaintained State records, so we don’t want this transform running just yet.  Click the X ion to delete the transform.  We’ll re-add it later.

![][image-17]
### Step 18


Most regions have multiple states.  Some have 1:1 relationships and there is only one state value that could be associated with that particular region.  Some of the records with empty State values have such a Region, so we can easily fill in the missing State values.  Specifically, these particular records have “National Capital” as Region.  

We’ll add a new WEL expression to do this. Check to see if Sate is empty and Region is “National Capital”.  If this is true, then write “DC” in as State.  Otherwise, retain the existing value of State.

The following WEL expression does this:
[State] = if(([Region] == "National Capital") && ([State] == ""), "DC", [State])

Don’t execute yet!


![][image-18]
### Step 19


You can’t input text with line breaks, but if you click the Format button, this will pretty print your WEL expression.  This makes editing complex expressions, with nested logic, MUCH easier.  

Now you can lick the checkmark to execute.

![][image-19]
### Step 20


Re-add your empty State filter.  Note that it now happens AFTER your Washington DC transform.  

![][image-20]
### Step 21


Update your mapping to map [ParkType] to NationalParkUnitType and click Next.

![][image-21]
### Step 22


In the validation step, you should not see any warnings now.

Click Run Import

![][image-22]
### Step 23


Click Finish

![][image-23]
### Step 24


You should see a fully successful import job in your import history.  Horay!

![][image-24]
### Step 25


Navigate back to the Model Structure view.  Congratulations!  Your model has a clean import job.

![][image-25]


## Summary

Congratulations!  You have familiarized yourself with basics of troubleshooting, changing, and re-executing load jobs.





























[image-1]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.01.png
[image-2]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.02.png
[image-3]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.03.png
[image-4]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.04.png
[image-5]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.05.png
[image-6]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.06.png
[image-7]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.07.png
[image-8]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.08.png
[image-9]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.09.png
[image-10]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.10.png
[image-11]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.11.png
[image-12]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.12.png
[image-13]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.13.png
[image-14]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.14.png
[image-15]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.15.png
[image-16]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.16.png
[image-17]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.17.png
[image-18]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.18.png
[image-19]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.19.png
[image-20]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.20.png
[image-21]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.21.png
[image-22]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.22.png
[image-23]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.23.png
[image-24]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.24.png
[image-25]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex3/images/Ex3.25.png

