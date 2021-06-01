---
layout: post
title: Populating-Data in WPF Navigation Pane control | Syncfusion
description: Learn here all about Populating-Data support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: Navigation Pane
documentation: ug
---

# Populating-Data in WPF Navigation Pane (GroupBar)

Data can be populated in the GroupBar control thought XAML, C#, or XML. The GroupBar control also supports binding to objects. The following sections describe how to implement these different forms of data population.

## Through XAML

Create a GroupBar control in XAML, as seen below.



{% highlight xaml %}

<syncfusion:GroupBar Name="groupBar1">

<syncfusion:GroupBarItem HeaderText="NewGroupBarItem1" IsSelected="True" >

<syncfusion:GroupView>

<syncfusion:GroupViewItem Text="New GroupViewItem" />

</syncfusion:GroupView>

</syncfusion:GroupBarItem>



<syncfusion:GroupBarItem HeaderText="NewGroupBarItem2" />



<syncfusion:GroupBarItem HeaderText="NewGroupBarItem3"  />



</syncfusion:GroupBar>

{% endhighlight %}

## Through  C#

To create a GroupBar control in  C# , include the following namespace to the directives list.



{% highlight C# %}

using Syncfusion.Windows.Tools.Controls;


{% endhighlight %}


Next, create the GroupBar as follows.



{% highlight C# %}

GroupBar gBar = new GroupBar();



GroupBarItem gBarItem1 = new GroupBarItem() { HeaderText ="NewGroupBarItem1", 					IsSelected = true };



GroupView gView = new GroupView();

GroupViewItem gViewItem = new GroupViewItem() { Text="New GroupViewItem"};

gView.Items.Add(gViewItem);



gBarItem1.Content = gView;



GroupBarItem gBarItem2 = new GroupBarItem() { HeaderText="NewGroupBarItem2"};

GroupBarItem gBarItem3 = new GroupBarItem() { HeaderText="NewGroupBarItem3"};



gBar.Items.Add(gBarItem1);

gBar.Items.Add(gBarItem2);

gBar.Items.Add(gBarItem3);



{% endhighlight %}



This will generate the following GroupBar control.



![Populating-Data_img1](Populating-Data_images/Populating-Data_img1.png)



