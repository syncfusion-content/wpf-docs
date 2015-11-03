---
layout: post
title: Adding Items to QuickAccesToolBar (QAT) | Ribbon | WPF | Syncfusion
description: Adding Items to QuickAccesToolBar (QAT)
platform: wpf
control: Ribbon
documentation: ug
---
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


## Add items from QAT Menu items

Ribbon also supports to add the items from QAT Menu items.To add the items to the Drop Down Menu of the QuickAccessToolBar, use the attached property, `QATMenuItems` of the Quick Access ToolBar .  QATMenuItems can be added to the QAT by making the Selection.

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


## Add items from QAT Customize Window

To open QAT Customize Window, select `MoreCommands` option from the ContextMenu of the QAT. In the QAT Customized Window, the list of Commands is available. The Commands can be filtered only from the Particluar tab by using `Choose commands from` option. Then, select the Command to add to the QuickAccessToolBar and add commands to the right Pane of the Quick Access ToolBar Dialog by clicking Add Button. Finally click OK.

![](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img4.jpeg)


![](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img5.jpeg)

Finally, the Items gets displayed in the QAT

![](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img6.jpeg)

## Add items from Ribbon context menu		
QAT can also customized by adding the items from the Ribbon ContextMenu. Select Add to Quick Access Toolbar by right clicking the Ribbon item required to add to the QAT. Then, the respective item gets added as one of the items in the QAT.

![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTML16431f9.PNG](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img7.jpeg)


![](AddingItemstoQuickAccessToolBar_images/AddingItemstoQuickAccessToolBar_img8.jpeg)

