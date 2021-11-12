# Exercise 2


## Estimated Time: 30 minutes

## Objective

In this exercise, you will configure and execute a data load job to get the first batch of data into your model.  You will be using the smart wrangler to do this.  


## What You Learn

*The load job workflow

*The basics of using the smart wrangler

*Using wrangler expressions



### Step 1


This is the model that you built in Exercise 1.  It has several measures and public dimensions, as well as a single local dimension.  The Data Foundation (Fact Table) is empty.  In this exercise, you will change that.

![][image-1]
### Step 2


Switch to the Data Management perspective, from the pulldown in the upper left.  

![][image-2]
### Step 3


Take a moment to familiarize yourself with this view.  The Details pane on the right side has been replaced with an import and export job history pane.  The main panel has the import and export jobs for this model.  Currently, the lists are empty.

![][image-3]
### Step 4


From the Import Job menu bar, in the upper right part of the import/export job panel, select the “Import Data From” pulldown and select Data Source.

![][image-4]
### Step 5


Since our data source is located on a shared Google Sheet, select Google Drive as the data source. 

![][image-5]
### Step 6


Select Google Sheet URL and enter the URL provided in the requirements section.

![][image-6]
### Step 7


Select Next.

![][image-7]
### Step 8


After a short while, the import job will be ready to configure.  Click “Set up import”.

![][image-8]
### Step 9


The next step in the import workflow is data wrangling.  You will automatically be switched to the smart wrangler.  Take a moment to familiarize yourself with the wrangling environment.  

The raw import data is shown in a spreadsheet style format in the main panel.  

There is a menu bar across the top.  

On the right side is the Details pane.  Like with the modeler, the details pane can be toggled between the dataset as a whole and the selected column.  When you initially come to the wrangler, there will be no selected column and you will only see Model Overview in the top of the Details pane.  The column details will become available when you select your first column.

Above the details panel is a pair of buttons, allowing you to toggle between Details and the Transform Log.  

![][image-9]
### Step 10


Some of the rows of data are missing values for State.  For the time being, we’ll simply filter them out.   Create your first transform, using the basic transform function.  Select the State column, then form the context menu, select Create a Transform.

![][image-10]
### Step 11


When focus changes to the Transform bar, select Filter,

![][image-11]
### Step 12


The filter function is already laid out for you.  A note here, you are creating a filter for KEEPING data, so if you leave the current “not matching” operator, you are creating a exclude filter.

![][image-12]
### Step 13


Click on the grey placeholder text and it will automatically change to an empty pair of quotes.  Hit enter to finish creating a filter.  This fill filter out records with empty values in State.

![][image-13]
### Step 14


We will now create our first [Wrangler Expression Language (WEL) expression](https://blogs.sap.com/2020/08/12/introduction-to-smart-data-wrangling/).  

To open the custom expression editor, click on the icon on the far right of the toolbar, in the Actions group.

This will add an editor space for the expression editor and the Details pane will be toggled to display help for editing.  This can be toggled off by clicking on the Help button, just to the left of the pane.  

![][image-14]
### Step 15


The data does not have a date column.  It does have Year and Month columns.  Let’s create a column called “Date”.  Column names in transforms are surrounded by brackets, as with formulas.  To create a new column called “Date”, write

[Date] =

Use the editor’s code completion functionality to help you create a concatenate statement.  Write

[Date] = co

Now, a list of functions will be displayed, starting with co.  Choose concatenate and it will be placed in your editor.


![][image-15]
### Step 16


We want each value of Date in a record to be drawn from Month and Year.  For string 1, write a “[” and all columns will be shown.  

![][image-16]
### Step 17


Make the expression show

[Date] = concatenate([Year], [Month], ".")

This will concatenate the values of Year and Month, using a period as the separator.  Then click the checkmark icon at the upper right of the editor to execute the transform.

![][image-17]
### Step 18


Add the following expression

[AddedDate] = now()

This will create a new, AddedDate column and fill it with the current date (when the import job executed)

![][image-18]
### Step 19


With the AddedDate column still selected, toggle the Transform Log on. 

![][image-19]
### Step 20


Now you can see all transforms specific to the AddedDate column.  They are displayed in order of execution.  Note that individual transforms can be edited and deleted at any time.

![][image-20]
### Step 21


If you click the tab to display the entire dataset, you can see all three active transforms in your import job dataset.

![][image-21]
### Step 22


Toggle back to Details and select the Date column.

![][image-22]
### Step 23


Look at the details of the date column.  Note data type and the histogram.  Important!  The histogram only includes data form the first 2000 rows.

![][image-23]
### Step 24


Change the data type of the Date column to Date

![][image-24]
### Step 25


Click Next at the bottom right and go to the mapping step.  Most of the columns were automatically mapped, but there are five remaining columns that still need to be mapped.

Map:
*The source column [Date] to the model dimension Date

*The source column [State] to the model dimension State

*The source column [UnitCode] to the model dimension NationalPark

*The source column [ParkType] to the model dimension UnitType

*The source column [AddedDate] to the model dimension AddedDate


![][image-25]
### Step 26


Once all columns are mapped, click on Next

![][image-26]
### Step 27


You are now in the data validation step, where you can review your data quality issues, before executing the load job.  Note there is a problem with the park type in approximately 16 thousand rows.  Ignore this error for now.  We will resolve it in Exercise 3.

![][image-27]
### Step 28


Click on Run Import

![][image-28]
### Step 29


This popup signals your last chance to change any settings, before executing.  Go ahead and click Finish

![][image-29]
### Step 30


After some time, the import job will finish.  There will be a series of icons, indicating the state of each step in the import workflow.  There is an orange warning icon in the last step, indication a problematic import job.  In the Import History pane, you see a single job with 60k rows imported and 16k rows rejected.  

![][image-30]
### Step 31


Return to the Model Structure view and have a look at the data foundation.  Note that it is no longer empty.

![][image-31]


## Summary

Congratulations!  You have familiarized yourself with the data ingestion workflow of SAP Analytics Cloud’s new model and with the smart wrangler.  You still have some problems in your load job, which will need to be fixed in Exercise 3.



































[image-1]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.01.png
[image-2]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.02.png
[image-3]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.03.png
[image-4]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.04.png
[image-5]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.05.png
[image-6]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.06.png
[image-7]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.07.png
[image-8]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.08.png
[image-9]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.09.png
[image-10]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.10.png
[image-11]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.11.png
[image-12]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.12.png
[image-13]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.13.png
[image-14]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.14.png
[image-15]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.15.png
[image-16]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.16.png
[image-17]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.17.png
[image-18]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.18.png
[image-19]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.19.png
[image-20]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.20.png
[image-21]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.21.png
[image-22]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.22.png
[image-23]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.23.png
[image-24]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.24.png
[image-25]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.25.png
[image-26]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.26.png
[image-27]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.27.png
[image-28]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.28.png
[image-29]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.29.png
[image-30]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.30.png
[image-31]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex2/images/Ex2.31.png

