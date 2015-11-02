---
layout: post
title: Customize Ribbon through RibbonContextMenu
description: Customize Ribbon through RibbonContextMenu
platform: wpf
control: Ribbon
documentation: ug
---
## Customize Ribbon through RibbonContextMenu

### Functions available in Ribbon ContextMenu

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


### Adding custom item to the ContextMenu

Ribbon Context Menu supports display of custom items. To add the custom item, set an attached property called **CustomContextMenuItems** of the RibbonContextMenu

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


### How to disable the RibbonContextMenu?

In order to disable the ContextMenu handle the “**RibbonContextMenuOpening**” event

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


