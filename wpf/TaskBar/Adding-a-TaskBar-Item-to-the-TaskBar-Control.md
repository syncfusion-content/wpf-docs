---
layout: post
title: Adding-a-TaskBar-Item-to-the-TaskBar-Control
description: adding a taskbar item to the taskbar control
platform: wpf
control: TaskBar
documentation: ug
---

# Adding a TaskBar Item to the TaskBar Control

The Task Bar Item is added to the Task Bar by using either XAML or C# coding. Use the following code to add a Task Bar Item to the Task Bar control.



[XAML]



&lt;!-- Adding TaskBar --&gt;

&lt;syncfusion:TaskBar Name="taskBar" &gt;



&lt;!-- Adding TaskBarItem --&gt;

&lt;syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1"&gt;

&lt;/syncfusion:TaskBarItem&gt;

&lt;/syncfusion:TaskBar&gt;





[C#]



//Creating an instance for TaskBar

TaskBar taskBar = new TaskBar();



//Creating an instance for TaskBarItem

TaskBarItem taskBarItem1 = new TaskBarItem();



//Setting the header of TaskBarItem1

taskBarItem1.Header = "TaskBarItem1";



//Adding the TaskBarItem to TaskBar

taskBar.Items.Add(taskBarItem1);



//Adding TaskBar as content of window

this.Content = taskBar; 



The following screen shot shows the TaskBar control with TaskBar Item.



{ ![](Adding-a-TaskBar-Item-to-the-TaskBar-Control_images/Adding-a-TaskBar-Item-to-the-TaskBar-Control_img1.jpeg) | markdownify }
{:.image }




Adding Content to TaskBar Item

To add text to the TaskBar Item, use the below code



[XAML]



&lt;!-- Adding TaskBar  --&gt;

&lt;syncfusion:TaskBar Name="taskBar" &gt;



&lt;!-- Adding TaskBarItem --&gt;

&lt;syncfusion:TaskBarItem Name="taskBarItem1" Header="TaskBarItem1"&gt;



&lt;!-- Adding content to TaskBarItem --&gt;

&lt;StackPanel Margin="10" HorizontalAlignment="Center" VerticalAlignment="Stretch"&gt;

&lt;TextBlock TextWrapping="Wrap"&gt; This TaskBar that have a TaskBarItem.&lt;/TextBlock&gt;

&lt;/StackPanel&gt;

&lt;/syncfusion:TaskBarItem&gt;

&lt;/syncfusion:TaskBar&gt;





[C#]



//Creating an instance for TaskBar

TaskBar taskBar = new TaskBar();



//Creating an instance for TaskBarItem

TaskBarItem taskBarItem1 = new TaskBarItem();



//Setting the header of TaskBarItem1

taskBarItem1.Header = "TaskBarItem1";



// Creating instance for TextBlock

TextBlock textBlock1 = new TextBlock();



// Adding text to textblock

textBlock1.Text = "This TaskBar that have a TaskBarItem.";



// Adding textblock to taskbaritem

taskBarItem1.Items.Add(textBlock1);          



//Adding the TaskBarItem to TaskBar

taskBar.Items.Add(taskBarItem1);             



//Adding TaskBar as content of window

this.Content = taskBar; 



> _Note: To display the TaskBar Item, you must already have the TaskBar in which you are going to add the TaskBar Item._

The following screen shot illustrates how text has been added to the TaskBar Item.



{ ![](Adding-a-TaskBar-Item-to-the-TaskBar-Control_images/Adding-a-TaskBar-Item-to-the-TaskBar-Control_img2.jpeg) | markdownify }
{:.image }




