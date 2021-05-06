---
layout: post
title: Changing Header Height in WPF Navigation Pane control | Syncfusion
description: Learn here all about Changing Header Height support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: GroupBar
documentation: ug
---

# Changing Header Height in WPF Navigation Pane (GroupBar)

Header Height of the GroupBar Item

The height of the each GroupBar item header is set using the ItemHeaderHeight property. This dependency property sets the height for each groupbar items header.

Use the below code to set this property.


{% tabs %}
{% highlight xaml %}
 <!-- Adding GroupBar -->
 <syncfusion:GroupBar Height="200" Width="230" ItemHeaderHeight="50" Name="groupBar"> 
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True">  
 <!-- Adding content for GroupBar item using panel -->  
 <StackPanel Orientation="Vertical">   
 <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>   
 <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>  
 <RadioButton Margin="4,2,2,2">Vertical</RadioButton>   
 <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>   
 <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>    
 <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>
 </StackPanel>  </syncfusion:GroupBarItem>  <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"> 
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
 //Set the height of GroupBar item headergroupBar.ItemHeaderHeight = 50;
 {% endhighlight %} 
{% endtabs %}




## Height of the Container that hosts the Selected Header 

HeaderHeight is a dependency property, which gets or sets the height of the topmost container that hosts the selected header.

Use the below code snippet to set this property.


{% tabs %}
{% highlight xaml %} 
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" HeaderHeight="20" Width="230" VisualMode="StackMode" Name="groupBar">
  <!-- Adding GroupBarItem -->  
  <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True">    
  <!-- Adding content for GroupBar item using panel -->   
  <StackPanel Orientation="Vertical">     
  <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>   
  <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>   
  <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      
  <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>    
  <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>     
  <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    
  </StackPanel>  </syncfusion:GroupBarItem>  
  <!-- Adding GroupBarItem -->  
  <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General">  
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
groupBar.HeaderHeight = 20; 
{% endhighlight %} 
{% endtabs %}

