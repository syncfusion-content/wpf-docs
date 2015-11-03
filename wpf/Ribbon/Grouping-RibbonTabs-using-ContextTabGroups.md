---
layout: post
title: Grouping RibbonTabs using ContextTabGroups | Ribbon | WPF | Syncfusion
description: Grouping RibbonTabs using ContextTabGroups
platform: wpf
control: Ribbon
documentation: ug
---
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


