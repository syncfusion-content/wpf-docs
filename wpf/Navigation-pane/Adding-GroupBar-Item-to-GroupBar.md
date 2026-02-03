---
layout: post
title: Adding GroupBar Item to GroupBar in WPF Navigation Pane | Syncfusion
description: Learn here all about Adding GroupBar Item to GroupBar support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: Navigation Pane
documentation: ug
---

# Adding GroupBar Item to GroupBar in WPF Navigation Pane (GroupBar)

GroupBar Item is added to the GroupBar using XAML or C# code. The following code illustrates this. 


{% tabs %}
{% highlight xaml %} 
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" Width="230" Name="groupBar"> 
 <!-- Adding GroupBarItem -->  
    <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem"/>
</syncfusion:GroupBar> 
 {% endhighlight %} 

{% highlight C# %} 
//Creating an instance of GroupBar
GroupBar groupBar = new GroupBar();
//Creating an instance of GroupBar
ItemGroupBarItem groupBarItem = new GroupBarItem();
//Setting header for GroupBar itemgroup
BarItem.Header = "GroupBarItem";
//Adding GroupBar item to GroupBar
groupBar.Items.Add(groupBarItem);
//Adding GroupBar to the window
this.Content = groupBar; 
{% endhighlight %} 
{% endtabs %}




![Adding-GroupBar-Item-to-GroupBar_img1](Adding-GroupBar-Item-to-GroupBar_images/Adding-GroupBar-Item-to-GroupBar_img1.jpeg)





N> To display the GroupBar Item, you must have a GroupBar in which you are going to add the GroupBar Item.



