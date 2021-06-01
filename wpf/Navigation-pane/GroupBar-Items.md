---
layout: post
title: GroupBar Items in WPF Navigation Pane control | Syncfusion
description: Learn here all about GroupBar Items support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: GroupBar
 documentation: ug
---

# GroupBar Items in WPF Navigation Pane (GroupBar)

This topic illustrates the how to work with group-bar items.

## Status of the GroupBar Item

You can enable or disable the dragging of items using the DraggingItemInProgress property. This is a dependency property which gets or sets the value indicating whether the dragging of the items is in progress.

Use the below code snippet to set this property.


{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" DraggingItemInProgress="True" Width="230" Name="groupBar"> 
 <!-- Adding GroupBarItem -->  
 <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem">    
 <!-- Adding content for GroupBar item using panel -->
 <StackPanel Orientation="Vertical">      
 <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/> 
 <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton> 
 <RadioButton Margin="4,2,2,2">Vertical</RadioButton>   
 <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>   
 <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>   
 <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton> 
 </StackPanel>  
 </syncfusion:GroupBarItem> 
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
//Setting the items in progress while dragging
groupBar.DraggingItemInProgress = true; 
{% endhighlight %} 
{% endtabs %}



## Cursor Type for the GroupBar Item

You can customize the cursor type of GroupBar item using the GroupBarItemCursorType property. This dependency property sets the type of cursor for the groupbar item. There are two types of built-in cursor types available for the GroupBar item. They are as follows.

* Default – default cursor type is displayed while moving the mouse over GroupBar item
* Hand – hand cursor type is displayed while moving the mouse over GroupBar item

Use the below code snippet to set this property.

{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" GroupBarItemCursorType="Hand"  Width="230" Name="groupBar"> 
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem">  
 <!-- Adding content for GroupBar item using panel -->  
 <StackPanel Orientation="Vertical">    
 <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>
 <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>   
 <RadioButton Margin="4,2,2,2">Vertical</RadioButton>  
 <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/>  
 <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>   
 <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>   
 </StackPanel>  
 </syncfusion:GroupBarItem>  
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
//Setting the cursor type for GroupBar item
groupBar.GroupBarItemCursorType = ItemCursorType.Hand; 
{% endhighlight %} 
{% endtabs %}



## Content Length of the GroupBar Item

You can also set the length of the content in GroupBar item. This is done using the ItemContentLength property. This dependency property sets the height or width available for the content of the selected item, i.e., it sets the height for the content, if GroupBar layout is _vertical_, and width for the content, if GroupBar layout is horizontal. 

Use the below code snippet to set this property.


{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" Width="230" ItemContentLength="100" Name="groupBar"> 
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
 </StackPanel> 
 </syncfusion:GroupBarItem> 
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
//Set the length of the content
groupBar.ItemContentLength = 100;
{% endhighlight %}
{% endtabs %}



## Hidden GroupBar Item

You can get the hidden GroupBar items and do some operation depending upon the visibility by using the property HiddenItemsCount. This dependency property gets the number of GroupBar items that are hidden.

Use the below code to set this property.



{% highlight C# %}



int count;



//Get the hidden GroupBar items

count=groupBar.HiddenItemsCount;


{% endhighlight %}



## Setting Corner Radius for the GroupBar Item

It is now possible to set the corner radius of GroupBar Items in the GroupBar by using the GroupBarItemCornerRadius property. This helps the user to specify the degree of roundness at the tip of the GroupBar. 

The following code examples illustrate how to set this property.

{% tabs %}
{% highlight xaml %}
<syncfusion:GroupBarItem HeaderText="Mailbox" GroupBarItemCornerRadius="20" ShowInGroupBar="True">
{% endhighlight %}

{% highlight C# %}
// Creating an instance of GroupBar.
GroupBar groupBar = new GroupBar();
// Creating an instance of GroupBar Item.
GroupBarItem groupBarItem = new GroupBarItem();
// Setting Header Text for GroupBar Item.
groupBarItem.HeaderText = "Mailbox";
// Setting Corner Radius For GroupBar Item.
groupBarItem.GroupBarItemCornerRadius = new CornerRadius(20d);
// Setting ShowInGroupBar property for GroupBar Item.
groupBarItem.ShowInGroupBar = true;
// Adding GroupBar Item to GroupBar.
groupBar.Items.Add(groupBarItem);
{% endhighlight %}
{% endtabs %}


Run the code. The following output is displayed.



![GroupBar-Items_img1](GroupBar-Items_images/GroupBar-Items_img1.jpeg)





