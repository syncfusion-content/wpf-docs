---
layout: post
title: Quick-Access-Toolbar
description: quick access toolbar
platform: wpf
control: Ribbon
documentation: ug
---

# Quick Access Toolbar

Quick Access Toolbar in the ribbon instance is used to group the most commonly used commands and access the commands easily without having to search for the command in the menu bar. QAT is easily customized using the built-in context menu and is placed above or below the ribbon.



{{ '![](Quick-Access-Toolbar_images/Quick-Access-Toolbar_img1.jpeg)' | markdownify }}
{:.image }




Common application commands like Save, Close, Print, and so on, are executed on the click of a button using the Command property of the ribbon button. Use the below code to add items to the Quick Access Toolbar. 



<table>
<tr>
<td>
[XAML]<ribbon:Ribbon.QuickAccessToolBar><ribbon:QuickAccessToolBar><ribbon:RibbonButton ribbon:Ribbon.KeyTip="1" Command="ApplicationCommands.Close"/><ribbon:RibbonButton ribbon:Ribbon.KeyTip="2" Command="ApplicationCommands.Save"></ribbon:QuickAccessToolBar></ribbon:Ribbon.QuickAccessToolBar></td></tr>
<tr>
<td>
[C#]RibbonButton rr = new RibbonButton();rr.SmallIcon = new BitmapImage(new Uri("/../SampleImages/Bold16.png", UriKind.Relative));rr.SizeForm = SizeForm.ExtraSmall;RibbonWindow.QuickAccessToolBar.Items.Add(rr);</td></tr>
</table>


Adding items using Quick Access Dialog

Commands are added to Quick Access Toolbar using the Quick Access Dialog. Quick Access Dialog is enabled by selecting more commands option in the context menu of QAT. The Quick Access Dialog displays the list of all available commands in the application. You can insert commands in the Quick Access Toolbar by adding the commands to the right pane of the Quick Access Dialog.



{{ '![](Quick-Access-Toolbar_images/Quick-Access-Toolbar_img2.jpeg)' | markdownify }}
{:.image }




See Also 

Menu Item Synchronization

## Menu Item Synchronization

Quick Access Toolbar MenuItem synchronized with Ribbon controls defined in RibbonBar, ApplicationMenu and Quick Access Toolbar. This can be achieved using SynchronizedItem property.

In order to synchronize QAT menu items with Ribbon controls, you have to set common string values for both the items i.e. the QAT menu item and Ribbon control. 

The following code sample illustrates how you can synchronize Quick Access Toolbar MenuItem with other Ribbon Controls by using SynchronizedItem property.



<table>
<tr>
<td>
[XAML]<syncfusion:Ribbon.ApplicationMenu>     <syncfusion:ApplicationMenu IsPopupOpen="False">          <syncfusion:SimpleMenuButton  Name="appMenuSave" Label="Save" Icon="/Save.png" syncfusion:RibbonCommandManager.SynchronizedItem="Save"/>     </syncfusion:ApplicationMenu></syncfusion:Ribbon.ApplicationMenu><syncfusion:QuickAccessToolBar.QATMenuItems><syncfusion:RibbonButton  Name="qatMenuSave" Label="Save" syncfusion:RibbonCommandManager.SynchronizedItem="Save"/></syncfusion:QuickAccessToolBar.QATMenuItems></td></tr>
<tr>
<td>
[C#]RibbonCommandManager.SetSynchronizedItem(appMenuSave, "Save");RibbonCommandManager.SetSynchronizedItem(qatMenuSave, "Save");</td></tr>
</table>


{{ '![](Quick-Access-Toolbar_images/Quick-Access-Toolbar_img3.jpeg)' | markdownify }}
{:.image }




