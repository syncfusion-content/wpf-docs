---
layout: post
title: Getting Started with Coded UI Testing for Syncfusion Essential WPF controls
description: Learn how to test with Coded UI for Syncfusion Essential WPF controls
platform: wpf
control: Testing
documentation: ug
---
# Getting Started with Coded UI Testing

CUIT contains the coded UI test project. When application does not contain the CUIT project, create a new project. In the Solutions Explorer, on the shortcut menu of the solution, choose Add, New Project, and then select either Visual Basic or Visual C#. Next, choose Test, Coded UI Test.

Coded UI test project does not appear on Visual Studio, if Visual Studio Enterprise edition not installed in the system. To create CUIT, install Visual Studio Enterprise edition in system.

![](CodedUI_images/CodedUI_img1.jpeg)


## Adding Coded UI Test file

The CUIT file is automatically generated, when create the Coded UI test project. To add another test file, right-click to the test project choose Add, and then select Coded UI Test.

![](CodedUI_images/CodedUI_img2.jpeg)


1.Generate Code for Coded UI Test dialog box is shown after select the Coded UI test file. Choose the Record option shown in the following image, to record the test actions.

![](CodedUI_images/CodedUI_img3.jpeg)


2.After choose the Record Actions, right-click the body of the Coded UI Test file. 

![](CodedUI_images/CodedUI_img4.jpeg)


Then choose the Coded UI Test Builder (UI Map), shown at the bottom right side of the window.

![](CodedUI_images/CodedUI_img5.jpeg)


3.Start the recording option from UI Map to record the test actions. 



### Click to Start the Recording.

Recording option can be paused while testing the project.


### Click to Stop the Recording.

4.The Recorded steps are shown by UI Map or by pressing Alt+ S key.

5.To delete actions that recorded by mistake, choose Edit Actions.

6.To generate code that replicates the action, choose the Generate Code icon and type a name and description for CUIT method.

![C:/Users/marimuthu.sivalingam/Documents/My Received Files/L_AA40.tmp.PNG](CodedUI_images/CodedUI_img6.jpeg)


7.After the completion of test process, click the Generate Code option from UI Map to generate the test code for project, as it replicates test actions.



### Generate Test Code 

8.Choose the required Method of Description for code generation then click to Add and Generate.

![](CodedUI_images/CodedUI_img7.jpeg)




## Testing application with the Generated Coded UI Tests.

Application can be tested with the generated CUIT method.

1.Add a test method called CodedUITestProject1.

{% tabs %}

{% highlight C# %}

public void CodedUITestMethod1()

{
// Generates code for this test. Select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
    this.UIMap.RecordedMethod2();
}

{% endhighlight %}

{% highlight VB %}

Public Sub CodedUITestMethod1()

' Generates code for this test. Select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
	Me.UIMap.RecordedMethod2()
End Sub 

{% endhighlight %}

{% endtabs %}

2.Build and run the application that has already been configured. CUIT builder can be opened with the following steps.

3.Right-click the body of the `CodedUITestMethod` and then select `Generate Code for Coded UI Test` -> Use CUIT builder as shown in the following screenshot:


![](CodedUI_images/CodedUI_img8.jpeg)


![](CodedUI_images/CodedUI_img9.jpeg)

## Supported controls

The following controls are featured in Coded UI Testing Support:

<table>
<tr>
<th>
Supported Controls<br/><br/></th>
<th>
Level<br/><br/></th></tr>
<tr>
<td>
CellGrid<br/><br/></td><td>
3 Level<br/><br/></td></tr>
<tr>
<td>
DataGrid<br/><br/></td><td>
3 Level<br/><br/></td></tr>
<tr>
<td>
TreeGrid<br/><br/></td><td>
2 Level<br/><br/></td></tr>
<tr>
<td>
GridDataControl<br/><br/></td><td>
2 Level<br/><br/></td></tr>
<tr>
<td>
Ribbon<br/><br/></td><td>
2 Level<br/><br/></td></tr>
<tr>
<td>
DockingManager<br/><br/></td><td>
2 Level<br/><br/></td></tr>
</table>


