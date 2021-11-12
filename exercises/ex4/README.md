# Exercise 4


## Estimated Time: 15 minutes

## Objective

In this exercise, you will create model based calculated measures.


## What You Learn

*Creating calculated measures in the model.





### Step 1


Your starting point is the model in the Model Structure view, as you left it at the end of Exercise 3.  Navigate to the Calculations view.

![][image-1]
### Step 2


Take a moment to familiarize yourself with this view.  

As in the other views, there is a toolbar across the top.

On the left side panel, you see the model’s measures and calculated measures.

In the upper center, you have the formula editor.

In the lower enter, you see a calculation preview.  Right now, it is showing an error, because there are no calculated measures in the model yet.

In the properties pane on the right side, you see the properties of the selected measure or calculated measure.

![][image-2]
### Step 3


Click the plus icon to add a new calculated measure.

![][image-3]
### Step 4


Your new calculated measure will contain the percentage of overnight visitors that camped in the wilderness, or at least had a backcountry permit for doing so.  To prevent overuse, protect the ecosystem and maintain the wilderness character in the backcountry, the US National Park Service rations designated backcountry campsites.

Give your new calculated measure a name: BackcountryPerentage

Give it a description: Percentage of overnight visitors with a backcountry camping permit

At the bottom of the properties pane, in the Formatting group, select Percentage as Scaling.

![][image-4]
### Step 5


You now have an empty calculated measure.  The editor is complaining that the formula is empty, and the calculation preview also still shows an error because of this.

![][image-5]
### Step 6


Start adding an IF statement in the formula.  Like with the WEL editor, there is code completion to help input the empty IF statement.

![][image-6]
### Step 7




![][image-7]
### Step 8


Type an open bracket, to make the measures available in the code completion.  Select [Backcountry]

![][image-8]
### Step 9


Input the following formula:

IF([Backcountry]>0, 1, 0)

Note that the calculation preview now shows a value.

![][image-9]
### Step 10


The current formula does not have much sematic meaning, so lets flesh it out:

If the value of [Backcountry] is zero, then the percentage will also be zero.  Otherwise, divide [Backcountry] by the sum of all overnight visitor types (all measures, except [RecreationalVisits])

![][image-10]
### Step 11


There should be no errors in your formula.  You can save the model now.  

![][image-11]


## Summary

You have familiarized yourself with basics of creating calculated measures in the model and have completed this set of hands-on exercises.  You now have a model with which you can perform basic analysis of visitation in US National Parks, and you have the basic skills needed to start creating your own new models.  Congratulations!  Feel free to add your model to a story and explore it!













[image-1]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.01.png
[image-2]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.02.png
[image-3]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.03.png
[image-4]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.04.png
[image-5]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.05.png
[image-6]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.06.png
[image-7]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.07.png
[image-8]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.08.png
[image-9]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.09.png
[image-10]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.10.png
[image-11]:    https://github.com/SAP-samples/teched2021-ANA261/raw/main/exercises/ex4/images/Ex4.11.png

