---
layout: post
title: Using Context menu in GroupBar in WPF Navigation Pane | Syncfusion
description: Learn here all about Using Context menu in GroupBar support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: Navigation Pane
 documentation: ug
---

# Using Context menu in GroupBar in WPF Navigation Pane (GroupBar)

To enable the context menu support in the GroupBar, set IsEnabledContextMenu property to _true_. This dependency property sets the value that indicates whether the context menu is enabled. 

Here are the benefits of using context menu in GroupBar control.

Use the following code snippet to set this property.

* Cut, copy and paste the content of GroupBar
* Sort the content of groupbar
* Add the GroupBarItem
* Rename the GroupBarItem
* Delete the GroupBarItem
* Move the content of GroupBar either up or down
* Add the content of GroupBar item.
* Rename the content of GroupBar item.
* Delete the content of GroupBar item.



{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar that has context menu -->
<syncfusion:GroupBar Height="250" Width="230" IsEnabledContextMenu="True" Name="groupBar"> 
 <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">
 <!-- Adding content for GroupBar item using GroupView --> 
 <syncfusion:GroupView>  
 <syncfusion:GroupViewItem Text="List View"/>    
 <syncfusion:GroupViewItem Text="Show ContextMenu"/> 
 <syncfusion:GroupViewItem Text="Show ToolTip"/> 
 </syncfusion:GroupView> 
 </syncfusion:GroupBarItem>
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode">   
 <!-- Adding content for GroupBar item using GroupView -->  
 <syncfusion:GroupView>   
 <syncfusion:GroupViewItem Text="Default"/>    
 <syncfusion:GroupViewItem Text="Multiple Expansion"/>  
 <syncfusion:GroupViewItem Text="StackMode"/>   
 </syncfusion:GroupView>  
 </syncfusion:GroupBarItem>
 </syncfusion:GroupBar>
 {% endhighlight %}

{% highlight C#  %}
//Enable the Context menu for GroupBar
groupBar.IsEnabledContextMenu = true;
{% endhighlight %}
{% endtabs %}




![Using-Context-menu-in-GroupBar_img1](Using-Context-menu-in-GroupBar_images/Using-Context-menu-in-GroupBar_img1.jpeg)



