---
layout: post
title: Adding-GroupBar-Item-to-GroupBar
description: adding groupbar item to groupbar
platform: wpf
control: GroupBar
documentation: ug
---

# Adding GroupBar Item to GroupBar

GroupBar Item is added to the GroupBar using XAML or C# code. The following code illustrates this. 



{% highlight xml %} <!-- Adding GroupBar --><syncfusion:GroupBar Height="200" Width="230" Name="groupBar">  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem"/></syncfusion:GroupBar> {% endhighlight %} 

{% highlight C# %} //Creating an instance of GroupBarGroupBar groupBar = new GroupBar();//Creating an instance of GroupBarItemGroupBarItem groupBarItem = new GroupBarItem();//Setting header for GroupBar itemgroupBarItem.Header = "GroupBarItem";//Adding GroupBar item to GroupBargroupBar.Items.Add(groupBarItem);//Adding GroupBar to the windowthis.Content = groupBar; {% endhighlight %} 





![](Adding-GroupBar-Item-to-GroupBar_images/Adding-GroupBar-Item-to-GroupBar_img1.jpeg)





N> To display the GroupBar Item, you must have a GroupBar in which you are going to add the GroupBar Item.



