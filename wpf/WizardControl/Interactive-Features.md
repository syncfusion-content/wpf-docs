---
layout: post
title: Interactive-Features
description: interactive features
platform: wpf
control: Wizard
documentation: ug
---

# Interactive Features

This section illustrates the following interactive feature of Wizard control. 

## Adding Wizard Page to the Wizard Control

You can add any number of wizard pages to the Wizard control. They are plenty of properties in the Wizard control that are used to customize the look and feel of the wizard page.

To add a wizard page to the Wizard control, use the below code



[XAML]



&lt;syncfusion:WizardControl Name="wizardControl"&gt;

    &lt;syncfusion:WizardPage Name="wizardPage"/&gt;

&lt;/syncfusion:WizardControl&gt;



[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);  





{ ![](Interactive-Features_images/Interactive-Features_img1.jpeg) | markdownify }
{:.image }




To add two wizard pages to the Wizard control, refer the below code



[XAML]



&lt;syncfusion:WizardControl Name="wizardControl"&gt;

    &lt;syncfusion:WizardPage Name="wizardPage1"/&gt;

    &lt;syncfusion:WizardPage Name="wizardPage2"/&gt;

&lt;/syncfusion:WizardControl&gt;



[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage1 = new WizardPage();

WizardPage wizardPage2 = new WizardPage();

wizardControl.Items.Add(wizardPage1);     

wizardControl.Items.Add(wizardPage2);



{ ![](Interactive-Features_images/Interactive-Features_img2.jpeg) | markdownify }
{:.image }




## Wizard Page

You can select the wizard page from the wizard control by using the SelectedWizardPage property.

To set this property, use the below code.



[XAML]



&lt;syncfusion:WizardControl Name="wizardControl" SelectedWizardPage="wizardPage2" Foreground="SlateBlue"&gt;

    &lt;syncfusion:WizardPage Name="wizardPage1" Title="WizardPage1"/&gt;

    &lt;syncfusion:WizardPage Name="wizardPage2" Title="WizardPage2"/&gt;

    &lt;syncfusion:WizardPage Name="wizardPage3" Title="WizardPage3"/&gt;

&lt;/syncfusion:WizardControl&gt;



[C#]



// "grid" is the name of grid control

WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage1 = new WizardPage();

WizardPage wizardPage2 = new WizardPage();

WizardPage wizardPage3 = new WizardPage();

wizardControl.Foreground = Brushes.SlateBlue;    

wizardPage1.Title = "Wizard Page1";

wizardPage2.Title = "Wizard Page2";

wizardPage3.Title = "WizardPage3";

wizardControl.Items.Add(wizardPage1);

wizardControl.Items.Add(wizardPage2);

wizardControl.Items.Add(wizardPage3);

wizardControl.SelectedWizardPage = wizardPage2; 



{ ![](Interactive-Features_images/Interactive-Features_img3.jpeg) | markdownify }
{:.image }


### Title and Description

You can set the title and description for the wizard page by using the Title and Description properties respectively.

Use the following code snippet to set these properties.



[XAML]



&lt;syncfusion:WizardControl Name="wizardControl"&gt;

    <syncfusion:WizardPage Name="wizardPage" Foreground="Navy" Title="WizardPage1"

Description="This is the first page of wizard" />

&lt;/syncfusion:WizardControl&gt;



[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardPage.Foreground = Brushes.Navy;

wizardPage.Title = "WizardPage1";

wizardPage.Description = "This is the first page of wizard"



{ ![](Interactive-Features_images/Interactive-Features_img4.jpeg) | markdownify }
{:.image }


### Wizard Page Type

You can set the type of the wizard page by using the PageType property. There are three types of wizard pages.

* Blank
* Interior
* Exterior



Use the below code snippet to set the PageType as Blank.



[XAML]



&lt;syncfusion:WizardControl Name="wizardControl"&gt;

    &lt;syncfusion:WizardPage Name="wizardPage" PageType="Blank"/&gt;

&lt;/syncfusion:WizardControl&gt;





[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardPage.PageType = WizardPageType.Blank;    



{ ![](Interactive-Features_images/Interactive-Features_img5.jpeg) | markdownify }
{:.image }




Use the following code snippet to set the PageType as Interior.



[XAML]



&lt;syncfusion:WizardControl Name="wizardControl"&gt;

    &lt;syncfusion:WizardPage Name="wizardPage" PageType="Interior"/&gt;

&lt;/syncfusion:WizardControl&gt;





[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardPage.PageType = WizardPageType.Interior;  



Use the following code snippet to set the PageType as Exterior.



[XAML]



&lt;syncfusion:WizardControl Name="wizardControl"&gt;

    &lt;syncfusion:WizardPage Name="wizardPage" PageType="Exterior"/&gt;

&lt;/syncfusion:WizardControl&gt;



[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardPage.PageType = WizardPageType.Exterior;    



{ ![](Interactive-Features_images/Interactive-Features_img6.jpeg) | markdownify }
{:.image }




See Also

Minimum Width for the Banner Image on the Exterior Wizard Page, Minimum Height for the Interior Wizard Page Header

### Navigation Buttons of Wizard Page

This topic illustrates the following about Navigation buttons:

* Enabling or Disabling the Navigation Buttons
* Showing or Hiding the Navigation Buttons
* Text for the Navigation Buttons



Enabling or Disabling the Navigation Buttons

You can enable or disable the Back, Cancel, Next and Finish navigation buttons in the wizard control and wizard page. This is done by using the BackEnabled, CancelEnabled, NextEnabled and FinishEnabled properties respectively.

Here is the code snippet.



[XAML]



<syncfusion:WizardControl Name="wizardControl" BackEnabled="True" FinishEnabled="True"

NextEnabled="True" CancelEnabled="True">

    &lt;syncfusion:WizardPage Name="wizardPage"/&gt;

&lt;/syncfusion:WizardControl&gt;



[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();           

wizardControl.Items.Add(wizardPage);

wizardControl.NextEnabled = true;

wizardControl.BackEnabled = true;

wizardControl.FinishEnabled = true;

wizardControl.CancelEnabled = true;  



{ ![](Interactive-Features_images/Interactive-Features_img7.jpeg) | markdownify }
{:.image }




Showing or Hiding the Navigation Buttons

You can show or hide the Back, Cancel, Next, Help and Finish navigation buttons in the wizard control and wizard page. This is done by using the BackVisible, CancelVisible, NextVisible, HelpVisible and FinishVisible properties respectively. 

To set these properties, refer the below code.



[XAML]



<syncfusion:WizardControl Name="wizardControl" BackVisible="False" NextVisible="True" 

CancelVisible="True" HelpVisible="True" FinishVisible="False">

    &lt;syncfusion:WizardPage Name="wizardPage"/&gt;

&lt;/syncfusion:WizardControl&gt;





[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardControl.CancelVisible = true;

wizardControl.BackVisible = false;

wizardControl.FinishVisible = true;

wizardControl.NextVisible = true;

wizardControl.HelpVisible = true; 



{ ![](Interactive-Features_images/Interactive-Features_img8.jpeg) | markdownify }
{:.image }




Text for the Navigation Buttons

You can set custom text for the Back, Next, Finish, Help and Cancel navigation buttons in the Wizard control. This is done by using the BackText, NextText, FinishText, HelpText and CancelText properties as follows. 



[XAML]



<syncfusion:WizardControl Name="wizardControl" BackText="Previous" 

HelpText="Help" CancelText="Exit" FinishText="Finish" NextText="Next">

    &lt;syncfusion:WizardPage Name="wizardPage"/&gt;

&lt;/syncfusion:WizardControl&gt;





[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();           

wizardControl.Items.Add(wizardPage);

wizardControl.NextText = "Next";

wizardControl.BackText = "Previous";

wizardControl.CancelText = "Exit";

wizardControl.HelpText = "Help";

wizardControl.FinishText = "Finish";



{ ![](Interactive-Features_images/Interactive-Features_img9.jpeg) | markdownify }
{:.image }


> _Note: You can set custom text for the navigation buttons in the wizard control only. You cannot set custom text for the navigation buttons in the wizard page._





See Also

Next Page and Previous Page Navigation

### Working with Wizard Control

This section contains the following topics:

#### Next Page and Previous Page Navigation

You can set the navigation to the Next and Previous pages by using the NextPage and PreviousPage properties respectively. To set these properties, use the below code.



[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage1 = new WizardPage();

WizardPage wizardPage2 = new WizardPage();

WizardPage wizardPage3 = new WizardPage();

wizardControl.Foreground = Brushes.SlateBlue;

wizardPage1.Title = "Wizard Page1";

wizardPage2.Title = "Wizard Page2";

wizardPage3.Title = "Wizard Page3";

wizardControl.Items.Add(wizardPage1);

wizardControl.Items.Add(wizardPage2);

wizardControl.Items.Add(wizardPage3);

wizardPage1.NextPage = wizardPage3;

wizardPage3.PreviousPage = wizardPage1;  



See Also

Navigation Buttons

#### Closing the Wizard Window

You can close the Wizard control window by clicking the Cancel or Finish button by enabling the CloseWindowOnCancel or CloseWindowOnFinish properties respectively.

To enable these properties, refer the below code



[XAML]



&lt;syncfusion:WizardControl Name="wizardControl" CloseWindowOnCancel="True" CloseWindowOnFinish="True"&gt;

    &lt;syncfusion:WizardPage Name="wizardPage"/&gt;

&lt;/syncfusion:WizardControl&gt;





[C#]



WizardControl wizardControl = new WizardControl();

grid.Children.Add(wizardControl);

WizardPage wizardPage = new WizardPage();

wizardControl.Items.Add(wizardPage);

wizardControl.CloseWindowOnCancel = true;

wizardControl.CloseWindowOnFinish = true; 



## Event for Next Button in Wizard Control  

The Next Button event has been implemented in Wizard Control in order to do operations such as displaying a message box and making the thread to sleep before navigating to the next page.

Use Case Scenario

Users can use this event to do valid code of operations such as displaying a message box and making the thread to sleep before navigating to the next page in Wizard Control.

Events



_Next Event Table_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th><th>
Reference links </th></tr>
<tr>
<th>
Next</th><th>
The Next button is clicked in Wizard Control</th><th>
-</th><th>
Routed Event</th><th>
-</th></tr>
</table>


Adding Next Button Event to an Application 



Use the following code snippet to define the Next Button Event for Wizard control:



[XAML]

		<syncfusion:WizardControl Name="wizardControl" 

                                        Next="wizardControl_Next">

&lt;!-- Welcome page --&gt;

			<syncfusion:WizardPage Name="wizPage1"                           Title="Welcome to the Installation Setup Wizard" PageType="Exterior"                                     

Description="This will install Software on your computer." BackVisible="False"

CancelVisible="True" FinishVisible="False" HelpVisible="True">



&lt;StackPanel Orientation="Vertical"&gt;

&lt;TextBlock TextWrapping="Wrap" Margin="0,10,10,10" Text="It is recommended that you close all other applications before continuing."/&gt;

&lt;TextBlock Margin="0,10,10,10" Text="Click Next to continue, or Cancel to exit Setup."/&gt;

&lt;TextBlock Margin="0,10,10,10" Text="For more information, click Help."/&gt;

&lt;/StackPanel&gt;



&lt;/syncfusion:WizardPage&gt;

                          &lt;/syncfusion:WizardControl&gt;



Samples Location

The samples are located in the following location:

[http://www.syncfusion.com/uploads/redirect.aspx?&team=support&file=WizardSample607850358.zip](http://www.syncfusion.com/uploads/redirect.aspx?&team=support&file=WizardSample607850358.zip)

