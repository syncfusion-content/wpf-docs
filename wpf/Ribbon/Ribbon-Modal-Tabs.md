---
layout: post
title: Ribbon-Modal-Tabs
description: ribbon modal tabs
platform: wpf
control: Ribbon
documentation: ug
---

# Ribbon Modal Tabs

Modal Tab in Ribbon Control displays a collection of commands that will be used only in a temporary mode. At this point, the core tabs will be disabled.

Use Case Scenarios

Print Preview is a Modal Tab which displays Print Preview related commands until you close the Modal Tab.



{ ![C:/Users/sureshkumarc/Desktop/modal Tabs/ModalTab10.png](Ribbon-Modal-Tabs_images/Ribbon-Modal-Tabs_img1.png) | markdownify }
{:.image }




{ ![C:/Users/sureshkumarc/Desktop/modal Tabs/Modal Tab2.png](Ribbon-Modal-Tabs_images/Ribbon-Modal-Tabs_img2.png) | markdownify }
{:.image }




Adding Modal Tabs to an Application 

You can add the Modal Tab in an application by adding Ribbon Tabs in ModalTabCollection property in Ribbon. You can also add all Ribbon Tabs that you want to use as Modal Tab into ModalTabCollection property. 

This is illustrated in the code given below.



[XAML]

            &lt;syncfusion:Ribbon.ModalTabCollection &gt;

                &lt;syncfusion:ModalTabCollection &gt;

                    <syncfusion:RibbonTab Caption="Print Preview" 

                                                 Name="printpreviewtab">

                        &lt;syncfusion:RibbonBar Header="Sample Bar"&gt;

                            <syncfusion:RibbonButton Label="Close Tab"                                                  

                                         Click="CloseModalTab_Click"/>

                        &lt;/syncfusion:RibbonBar&gt;

                    &lt;/syncfusion:RibbonTab&gt;

                &lt;/syncfusion:ModalTabCollection&gt;

            &lt;/syncfusion:Ribbon.ModalTabCollection&gt;





After adding this collection in Ribbon, you can then handle the Modal Tab visibility by using the following methods at any time.

Tables for properties, methods



Properties



_ModalTabCollection Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td><td>
Default Value</td></tr>
<tr>
<td>
ModalTabCollection</td><td>
Used to store the collection of Ribbon Tabs as Modal Tabs Collection.</td><td>
 Dependency Property</td><td>
ModalTabsCollection </td><td>
Null Collection</td></tr>
</table>


Methods



_ShowModalTab Table_

<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Return Type </th><th>
Reference links </th></tr>
<tr>
<th>
ShowModalTab</th><th>
This method will show the specific Modal Tab in the Ribbon from ModalTabCollection. </th><th>
(string arg1) arg1- Name of the Ribbon Tab to be displayed as Modal Tab from ModalTabCollection.</th><th>
bool </th><th>
How to Show a ModalTab?</th></tr>
</table>


_CloseModalTabs Table_

<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Return Type </th><th>
Reference links </th></tr>
<tr>
<th>
CloseModalTabs</th><th>
CloseModalTabs method will close the opened Modal Tabs in Ribbon control.</th><th>
 No Params</th><th>
bool </th><th>
How to close ModalTabs?</th></tr>
</table>


How to handle Modal Tabs in Ribbon?

You can add Ribbon Tabs that you want to display as Modal Tabs to ModalTabCollection property in the Ribbon Control. The ShowModalTab and CloseModalTabs methods handle Modal Tabs in the Ribbon control. You can display any Modal Tab from the ModalTabCollection property whenever required. 

You can call ShowModalTab method to show the specific Modal Tab in Ribbon. This can be done from any event of core Ribbon Tab element.

This is illustrated in the code given below.



[C#]



private void ShowModalTabBtn_Click(object sender, RoutedEventArgs e)

        {

            this.MyRibbon.ShowModalTab("printpreviewtab");

        }





CloseModalTabs method will close the currently opened Modal Tab in Ribbon control. This method should be called in any event of currently displaying Modal Tab element.

This is illustrated in the code given below.



[C#]



private void CloseModalTabBtn_Click(object sender, RoutedEventArgs e)

        {

            this.MyRibbon.CloseModalTabs();

        }



Sample Link

Tools  Ribbon   Modal Tabs

