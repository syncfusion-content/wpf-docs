---
layout: post
title: Dealing With Ribbon | Ribbon | WPF | Syncfusion
description: Three types of RibbonState
platform: wpf
control: Ribbon
documentation: ug
---
# Dealing With Ribbon

Ribbon can be changed into three different states such as `Normal`, `Hide` and `Adorner`

## Three types of RibbonState


`Normal` – Ribbon control will be in Normal State. This is the default state 

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

# Grouping RibbonTabs using ContextTabGroups

ContextualTabGroups are used to group the RibbonTabs for easy Navigation. This ContextTabGroups will appear when a user enable their context. 

## Creating ContextTabGroup 


This ContextTabGroup can also be kept hidden and shown while required cases like in Word Document’s TABLETOOLS ContextTabGroups which will get displayed automatically, while selecting the table.  The following code snippet used to create a ContextTabGroup

{% highlight xml %}

[XAML]

<syncfusion:Ribbon.ContextTabGroups>

<syncfusion:ContextTabGroup Label="Table tools" IsGroupVisible="True" BackColor="Green">

<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />

<syncfusion:RibbonTab Caption="Design" IsChecked="False" />

</syncfusion:ContextTabGroup>

</syncfusion:Ribbon.ContextTabGroups>



{% endhighlight %}

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img1.jpeg)


## Multiple ContextTabs

To differentiate one ContextTabGroup with one another, change its `BackColor` property of the ContextTabGroup , Since a ContextTabGroup Support to have multiple context Tab.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon.ContextTabGroups>

<syncfusion:ContextTabGroup Label="Table Tools" BackColor="Green" IsGroupVisible="True">

<syncfusion:RibbonTab Caption="Tables" IsChecked="False" />

<syncfusion:RibbonTab Caption="Design" IsChecked="False" />

</syncfusion:ContextTabGroup>

<syncfusion:ContextTabGroup Label="Table Grid" BackColor="Red" IsGroupVisible="True">

<syncfusion:RibbonTab Caption="Tables" IsChecked="False" />

<syncfusion:RibbonTab Caption="Design" IsChecked="False" />

</syncfusion:ContextTabGroup>

</syncfusion:Ribbon.ContextTabGroups>



{% endhighlight %}

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img2.jpeg)


## ContextTabGroup Heading

The `Label` property of the ContextTabGroup is used to define the Heading for the ContextTabGroup. 

{% highlight xml %}

[XAML]

<syncfusion:Ribbon.ContextTabGroups>

<syncfusion:ContextTabGroup Label="Table tools" BackColor="Green" IsGroupVisible="True">

<syncfusion:RibbonTab Caption="Tables" IsChecked="False" />

<syncfusion:RibbonTab Caption="Design" IsChecked="False" />

</syncfusion:ContextTabGroup>

</syncfusion:Ribbon.ContextTabGroups>



{% endhighlight %}

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img3.jpeg)




## Changing the visibility at run time

ContextTabgroup visibility can also be changed at the runtime. To change the visibility, enable `IsGroupVisible` property of the ContextTabGroup

{% highlight xml %}

[XAML]

<syncfusion:Ribbon  VerticalAlignment="Top" >

<syncfusion:Ribbon.ContextTabGroups>

<syncfusion:ContextTabGroup x:Name="tableContextTabGroup" Label="Table tools" BackColor="Red"  >

<syncfusion:RibbonTab Caption="Tables" IsChecked="False" >

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="Design" IsChecked="False" >

</syncfusion:RibbonTab>

</syncfusion:ContextTabGroup>

</syncfusion:Ribbon.ContextTabGroups>

</syncfusion:Ribbon>


{% endhighlight %}

{% highlight c# %}

[C#]

private void Button_Click(object sender, RoutedEventArgs e)

{

tableContextTabGroup.IsGroupVisible = true;

}



{% endhighlight %}

The output of the above code is illustrated in the following screenshot

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img4.jpeg)


After the Button is clicked, the ContextTabGroup visibility will change as follows

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img5.jpeg)


