---
layout: post
title: Adding-GroupBar-Item-to-GroupBar
description: adding groupbar item to groupbar
platform: wpf
control: GroupBar
documentation: ug
---

# Adding GroupBar Item to GroupBar

GroupBar Item is added to the GroupBar using XAML or {% highlight C# %} code. The following code illustrates this. 



<table>
<tr>
<td>
{% highlight xml %} <!-- Adding GroupBar --><syncfusion:GroupBar Height="200" Width="230" Name="groupBar">  <!-- Adding GroupBarItem -->  <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem"/></syncfusion:GroupBar> {% endhighlight %} </td></tr>
<tr>
<td>
{% highlight C# %} //Creating an instance of GroupBarGroupBar groupBar = new GroupBar();//Creating an instance of GroupBarItemGroupBarItem groupBarItem = new GroupBarItem();//Setting header for GroupBar itemgroupBarItem.Header = "GroupBarItem";//Adding GroupBar item to GroupBargroupBar.Items.Add(groupBarItem);//Adding GroupBar to the windowthis.Content = groupBar; {% endhighlight %} </td></tr>
</table>




![](Adding-GroupBar-Item-to-GroupBar_images/Adding-GroupBar-Item-to-GroupBar_img1.jpeg)





Note: To display the GroupBar Item, you must have a GroupBar in which you are going to add the GroupBar Item.



