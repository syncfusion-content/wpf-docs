---
layout: post
title: Three types of RibbonState
description: Three types of RibbonState
platform: wpf
control: Ribbon
documentation: ug
---
# Three types of RibbonState

Ribbon can be changed into three different states such as `Normal`, `Hide` and `Adorner`

### RibbonState enum property


`Normal` **–** Ribbon control will be in Normal State. This is the default state 

{% highlight xml %}

[XAML]

<syncfusion:Ribbon  RibbonState="Normal" VerticalAlignment="Top" x:Name="Ribbon" >

<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >

<syncfusion:RibbonBar  Header="Acions">

<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>

<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >

<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>

<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>

</syncfusion:SplitButton>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Header="Properties">

<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>

{% endhighlight %}

![](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img1.jpeg)

`Hide` **-**Ribbon control will move to the Hidden State

{% highlight xml %}

[XAML]

<syncfusion:Ribbon  RibbonState="Hide" VerticalAlignment="Top" x:Name="Ribbon" >

<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >

<syncfusion:RibbonBar  Header="Acions">

<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>

<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >

<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>

<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>

</syncfusion:SplitButton>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Header="Properties">

<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>

{% endhighlight %}

![](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img2.jpeg)


`Adorner` **–**In this state,ribbon will adorned above the content

{% highlight xml %}

[XAML]

<syncfusion:Ribbon  RibbonState="Adorner" VerticalAlignment="Top" x:Name="Ribbon" >

<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >

<syncfusion:RibbonBar  Header="Acions">

<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>

<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >

<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>

<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>

</syncfusion:SplitButton>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Header="Properties">

<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>

{% endhighlight %}

![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTML7d9bdf5.PNG](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img3.jpeg)

## How to change the RibbonState in run time?

Ribbon State can also be changed at the Runtime.In the below code, Ribbon State has been changed dynamically in the button click event

{% highlight c# %}

[C#]

Ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Normal;

{% endhighlight %}

{% highlight c# %}

[C#]

Ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Hide;

{% endhighlight %}

{% highlight c# %}

[C#]

Ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Adorner;

{% endhighlight %}

