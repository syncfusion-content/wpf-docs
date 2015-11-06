---
layout: post
title: Ribbon Customization | Ribbon | WPF | Syncfusion 
description: Customize Ribbon through RibbonContextMenu
platform: wpf
control: Ribbon
documentation: ug
---
# Customize Ribbon through RibbonContextMenu

RibbonContextMenu allows to customize the Ribbon with the Right Click and it displays different functions for Ribbon and RibbonItems.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon x:Name="Ribbon"  VerticalAlignment="Top">

<syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:QuickAccessToolBar syncfusion:WindowChrome.IsHitTestVisibleInChrome="True"/>

</syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:RibbonTab Caption="Home" >

<syncfusion:RibbonBar   Header="Clipboard"  >

<syncfusion:RibbonButton  Label="Paste" SizeForm="Large" LargeIcon="/Resources/Paste32.png"  />

<syncfusion:RibbonButton  Label="Cut" SizeForm="Small" SmallIcon="/Resources/Cut16.png" />

<syncfusion:RibbonButton  Label="Copy" SizeForm="Small"  SmallIcon="/Resources/Copy16.png"  />

<syncfusion:RibbonButton  Label="Format Painter" SizeForm="Small"  

SmallIcon="/Resources/FormatPainter16.png"  />

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>



{% endhighlight %}

The below RibbonContextMenu will be generated when the user right click on the ribbon

![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLcc26813.PNG](CustomizeRibbonthroughRibbonContextMenu_images/CustomizeRibbonthroughRibbonContextMenu_img1.jpeg)


It displays along with "Add to Quick Access ToolBar" function while clicking at the RibbonItem as like in the below screenshot

![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLcc2d14d.PNG](CustomizeRibbonthroughRibbonContextMenu_images/CustomizeRibbonthroughRibbonContextMenu_img2.jpeg)


## Adding custom item to the ContextMenu

Ribbon Context Menu supports display of custom items. To add the custom item, set an attached property called `CustomContextMenuItems` of the RibbonContextMenu

{% highlight xml %}

[XAML]

<syncfusion:Ribbon x:Name="Ribbon"  VerticalAlignment="Top" syncfusion:RibbonContextMenu.IsCustomContextMenuItemsOnTop="True" >

<syncfusion:RibbonContextMenu.CustomContextMenuItems >

<syncfusion:RibbonMenuItem Header="Edit" IsCheckable="True" />



<syncfusion:RibbonMenuItem Header="Delete" IsCheckable="True"  />

<syncfusion:RibbonMenuItem Header="Rename" IsCheckable="True"  />

</syncfusion:RibbonContextMenu.CustomContextMenuItems>

</syncfusion:Ribbon>



{% endhighlight %}


![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLcd86ccb.PNG](CustomizeRibbonthroughRibbonContextMenu_images/CustomizeRibbonthroughRibbonContextMenu_img3.jpeg)


## How to disable the RibbonContextMenu

In order to disable the ContextMenu handle the `RibbonContextMenuOpening` event

{% highlight xml %}

[XAML]

<syncfusion:Ribbon x:Name="Ribbon"  VerticalAlignment="Top"  RibbonContextMenuOpening="Ribbon_ContextMenuOpening">



<syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:QuickAccessToolBar syncfusion:WindowChrome.IsHitTestVisibleInChrome="True"/>

</syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:RibbonTab Caption="Home"  >

<syncfusion:RibbonBar Header="Clipboard" >

<syncfusion:RibbonButton Label="Paste" SizeForm="Large"

LargeIcon="/Resources/Paste32.png" />                    

<syncfusion:RibbonButton  Label="Cut" SizeForm="Small"   SmallIcon="/Resources/Cut16.png" />

<syncfusion:RibbonButton  Label="Copy" SizeForm="Small"  SmallIcon="/Resources/Copy16.png"  />

<syncfusion:RibbonButton  Label="Format Painter" SizeForm="Small"  

SmallIcon="/Resources/FormatPainter16.png"  />

</syncfusion:RibbonBar>      

</syncfusion:RibbonTab>

</syncfusion:Ribbon>



{% endhighlight %}



{% highlight c# %}

[C#]

private void Ribbon_ContextMenuOpening(object sender, ContextMenuEventArgs e)

{

e.Handled = true;

}



{% endhighlight %}

The following snapshot will be generated before handling the RibbonContextMenu event

![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLce6a396.PNG](CustomizeRibbonthroughRibbonContextMenu_images/CustomizeRibbonthroughRibbonContextMenu_img4.jpeg)


After the event is handled, the output will display as follows

![](CustomizeRibbonthroughRibbonContextMenu_images/CustomizeRibbonthroughRibbonContextMenu_img5.jpeg)


# Add Items to QuickAccesToolBar (QAT)

Quick Access Toolbar is used to group the frequently used commands above or under the Ribbon, and it allows to add or remove commands to it. It is placed next to the ApplicationMenu to provide end users with the easy accessibility.

## Add default QAT items

Use the following code to add items to the QuickAccessToolbar

{% highlight xml %}

[XAML]

<syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:QuickAccessToolBar>

<syncfusion:RibbonButton Label="Undo" SmallIcon="/Resources/Undo16.png" SizeForm="ExtraSmall"   

ToolTip="Undo" syncfusion:RibbonCommandManager.SynchronizedItem="Undo" />

<syncfusion:RibbonButton Label="Redo" SmallIcon="/Resources/Redo16.png" SizeForm="ExtraSmall"

ToolTip="Redo" syncfusion:RibbonCommandManager.SynchronizedItem="Redo"/>



</syncfusion:QuickAccessToolBar>

</syncfusion:Ribbon.QuickAccessToolBar>



{% endhighlight %}

{% highlight c# %}

[C#]

RibbonButton RibbonButton = new RibbonButton();

RibbonButton.SmallIcon = new BitmapImage(new Uri("/Resources/Redo16.png", UriKind.Relative));

RibbonButton.SizeForm = SizeForm.ExtraSmall;



QuickAccessToolBar QAT=new QuickAccessToolBar();

QAT.Items.Add(RibbonButton);

Ribbon.QuickAccessToolBar = QAT;



{% endhighlight %}

![](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img1.jpeg)


## Add items to QAT Menu items

Ribbon also supports to add the items to QAT Menu items. To add the items to the Drop Down Menu of the QuickAccessToolBar, use the attached property, `QATMenuItems` of the Quick Access ToolBar .  QATMenuItems can be added to the QAT by making the Selection.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:QuickAccessToolBar>

<syncfusion:QuickAccessToolBar.QATMenuItems>

<syncfusion:RibbonButton Label="Save" syncfusion:RibbonCommandManager.SynchronizedItem="Save" />

<syncfusion:RibbonButton Label="Quick Print" syncfusion:RibbonCommandManager.SynchronizedItem="Quick Print"/>

<syncfusion:RibbonButton Label="Print Preview" syncfusion:RibbonCommandManager.SynchronizedItem="Print Preview"/>

<syncfusion:RibbonButton Label="Undo" syncfusion:RibbonCommandManager.SynchronizedItem="Undo"  />

<syncfusion:RibbonButton Label="Redo" syncfusion:RibbonCommandManager.SynchronizedItem="Redo" />

<syncfusion:RibbonButton Label="Paste" syncfusion:RibbonCommandManager.SynchronizedItem="Paste"/>

</syncfusion:QuickAccessToolBar.QATMenuItems>



<syncfusion:RibbonButton Label="Undo" SmallIcon="/Resources/Undo16.png" SizeForm="ExtraSmall"   

ToolTip="Undo" syncfusion:RibbonCommandManager.SynchronizedItem="Undo" />

<syncfusion:RibbonButton Label="Redo" SmallIcon="/Resources/Redo16.png" SizeForm="ExtraSmall"

ToolTip="Redo" syncfusion:RibbonCommandManager.SynchronizedItem="Redo"/>



</syncfusion:QuickAccessToolBar>

</syncfusion:Ribbon.QuickAccessToolBar>



{% endhighlight %}

{% highlight c# %}

[C#]

RibbonButton pasteRibbonButton = new RibbonButton() { Label = "Paste", SmallIcon = new BitmapImage(new Uri("/Resources/Paste32.png", UriKind.Relative))};



this.Ribbon.QuickAccessToolBar.QATMenuItems.Add(pasteRibbonButton);



{% endhighlight %}

The “Paste” QATMenuItem has been selected and it is displayed as one of the items in the QAT. 

![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTML6da0b2.PNG](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img2.jpeg)


![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTML6d3ac4.PNG](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img3.jpeg)


## Add items to QAT Customize Window

To open QAT Customize Window, select `MoreCommands` option from the ContextMenu of the QAT. In the QAT Customized Window, the list of Commands is available. The Commands can be filtered only from the Particluar tab by using `Choose commands from` option. Then, select the Command to add to the QuickAccessToolBar and add commands to the right Pane of the Quick Access ToolBar Dialog by clicking Add Button. Finally click OK.

![](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img4.jpeg)


![](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img5.jpeg)

Finally, the Items gets displayed in the QAT

![](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img6.jpeg)

## Add items from Ribbon context menu		
QAT can also customized by adding the items from the Ribbon ContextMenu. Select Add to Quick Access Toolbar by right clicking the Ribbon item required to add to the QAT. Then, the respective item gets added as one of the items in the QAT.

![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTML16431f9.PNG](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img7.jpeg)


![](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img8.jpeg)

# Add custom RibbonTab and RibbonBar

The following section illustrates how to customize Ribbon at the run time

### QAT Customized Window

This topic illustrates in detail about the QAT topic.

First, select MoreCommands option from the QAT to open the QAT Customized Window.

QAT can be Customized further by using the following options

1. Add

	In the QAT Customized window, the list of Commands is available. The Commands can be filtered only from the Particluar tab by using `Choose commands from` option. Then, select the commands to be added to the QAT and add the command to Right Pane of the QAT Dialog by clicking `Add` Button. Finally, Click Ok. Now, the selected command gets added in the QAT.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img1.jpeg)

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img2.jpeg)

2. Remove

	QAT items can be removed at the Run time. In the QAT Customize window, select the Command to be deleted from the QAT Dialog,and then click Remove Button. In the following screenshot, Redo command gets deleted and the output is changed according to it.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img3.jpeg)

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img4.jpeg)

3. Reset

	To restore the QAT to its default content, use this `Reset` option.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLb81ba81.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img5.jpeg)

4. Reorder

	QAT also supports to reorder the items by clicking the Up and down arrow at the left of the QAT Dialog. 

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img6.jpeg)

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img7.jpeg)


### Customize Ribbon with RibbonTab and RibbonBar

QAT can also support to customize Ribbon Tab and RibbonBar while running. To customize the Ribbon, enable the `ShowCustomizeRibbon` property of the Ribbon to `true` and follow the steps. 

1. Click the Quick Access Toolbar drop-down button and click the `MoreCommands` menu.

2. Then, select the `Customize Ribbon` options from the left-side column.

3. You can add `Ribbontab` and `Ribbonbar` by selecting New Tab and New Group Options Respectively.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img8.jpeg)

4. To move the tab up and down, select the tab to be moved and click the button at the right-side corner accordingly. Similarly, the group can be moved within the tab.

5. By using the `Rename` option, rename any particular Tab/Group present in the Ribbon by selecting it.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLb9b87bb.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img9.jpeg)

6. The visibility of any particular Tab can be changed by enabling the checkbox of the corresponding selection.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img10.jpeg)

7. By using `Delete` option, the Custom RibbonBar and RibbonTab can be deleted. But, this option does not work in the case of original content.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLb9c3957.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img11.jpeg)

8. To delete all the Ribbon Customization, use `Reset All Customization` from the Reset Drop Down Menu.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLb9d29e2.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img12.jpeg)

After customizing the RibbonTab and RibbonBar, RibbonItems can be customized. Customizing Ribbon Item concepts are explained as follows.

## Add items to the customized RibbonTab

The steps to customize the Ribbon Item are as follows

1. The `Choose commands from` drop-down list is used to filter the commands only from the Particular Tab.

2.  To add the item under the right-side column of a newly added `Ribbonbar` and `Ribbontab`, select the item from left-side column and click the `Add` button.

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLba692c1.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img13.jpeg)

3. Also, the Ribbon Item from the RibbonBar can be removed that is added recently by using `Remove` option

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLbb23805.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img14.jpeg)

4. The order of the RibbonItem within the RibbonBar can be changed by using `Up` and `Down` arrow

5. By using the Rename option,the RibbonIrem can be renamed

	![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTMLbb2d36a.PNG](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img15.jpeg)

6. Click `OK` button. The Changes are reflected in the output window.

	![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img16.jpeg)


## How to disable the customization in Ribbon?

To disable the customization in the Ribbon, set `ShowCustomizeRibbon` property of the Ribbon as `False` 

{% highlight xml %}

[XAML]

<syncfusion:Ribbon  VerticalAlignment="Top" x:Name="Ribbon" ShowCustomizeRibbon="False">

<syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:QuickAccessToolBar >

<syncfusion:RibbonButton Label="Undo" SmallIcon="/Resources/Undo16.png" SizeForm="ExtraSmall"   

ToolTip="Undo" syncfusion:RibbonCommandManager.SynchronizedItem="Undo" />

<syncfusion:RibbonButton Label="Redo" SmallIcon="/Resources/Redo16.png" SizeForm="ExtraSmall"

ToolTip="Redo" syncfusion:RibbonCommandManager.SynchronizedItem="Redo"/>

</syncfusion:QuickAccessToolBar>

</syncfusion:Ribbon.QuickAccessToolBar>

<syncfusion:RibbonTab  Caption="HOME" >

<syncfusion:RibbonBar  Header="Respond">

<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>

<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>

<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>

<syncfusion:RibbonButton   Label="Paste" SizeForm="Large" SmallIcon="/Resources/Paste32.png" syncfusion:RibbonCommandManager.SynchronizedItem="Paste" />

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="SEND/RECIEVE"/>

</syncfusion:Ribbon>
{% endhighlight %}


In the following screenshot, customizing Ribbon is disabled and it shows only the QAT Customize window



![](AddingcustomRibbonTabandRibbonBar_images/AddingcustomRibbonTabandRibbonBar_img17.jpeg)

