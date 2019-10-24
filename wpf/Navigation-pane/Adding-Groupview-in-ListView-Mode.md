---
layout: post
title: Adding Groupview in ListView Mode| GroupBar | WPF | Syncfusion
description: This section describes how to arrange group view items in list view mode of GroupBar Control using programmatically.
platform: wpf
control: GroupBar
documentation: ug
---

# Add GroupView in ListView Mode

You can arrange GroupView Items in list view mode by using the IsListViewMode property. This property is used to enable or disable the layout of items in a GroupView in the ListView mode.

You can arrange GroupView items in list view mode using the following code.


{% tabs %}
{% highlight xaml %} 
<!-- Adding GroupBar that have visual mode is Multiple Expansion -->
<syncfusion:GroupBar Height="300" Width="230" Name="groupBar"> 
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem1"  Header="General">  
 <!-- Adding content for GroupBar item using GroupView -->  
 <syncfusion:GroupView Name="groupView" IsListViewMode="True"> 
 <syncfusion:GroupViewItem Text="List View"/>  
 <syncfusion:GroupViewItem Text="Show ContextMenu"/>   
 <syncfusion:GroupViewItem Text="Show ToolTip"/>  
 </syncfusion:GroupView>
 </syncfusion:GroupBarItem>
 </syncfusion:GroupBar> 
 {% endhighlight %} 

{% highlight C# %}
 groupview.IsListViewMode = true;
 {% endhighlight %} 
{% endtabs %}


{% seealso %}

GroupView Orientation in Orientation topic.

{% endseealso %}