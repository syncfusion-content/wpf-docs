---
layout: post
title: State Persistence in WPF Navigation Pane control | Syncfusion
description: Learn here all about State Persistence support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: GroupBar
documentation: ug
---

# State Persistence in WPF Navigation Pane (GroupBar)

The bar state can be persisted in the GroupBar control using the bar state methods available. You can set three different state persistence in the GroupBar. The three state persistence are as follows.

* Save State – Saves the state persisted for the current GroupBar location. This can be done using the SaveBarState method.
* Load State – Loads the state that is persisted. This can be done using the LoadBarState method.
* Reset State – Resets the state that is persisted. This can be done using the ResetBarState method.

You can set the state persistence using the following code.



{% highlight C# %}



// Save State

myGroupBar.SaveBarState();



// Load State

myGroupBar.LoadBarState();

registerEvents(myGroupBar);



// Reset State

myGroupBar.ResetBarState();

registerEvents(myGroupBar);
{% endhighlight %}


The ResetBarState method is used to register the events. The following code illustrates this.



{% highlight C# %}



public void registerEvents(Syncfusion.Windows.Tools.Controls.GroupBar groupBar)

{

if (groupBar != null)

{

foreach (GroupBarItem tab in groupBar.Items)

{

SubscribeToTabEvents(tab);

if (tab.Content is GroupView)

{

GroupView view = tab.Content as GroupView;

if (view != null)

{

foreach (GroupViewItem item in view.Items)

{

SubscribeToItemEvents(item);

}

}

}

}

}

}

{% endhighlight %}

You can also save the state persisted on loading the GroupBar. By using the SaveOriginalState property, you can enable the saving the state on loading. This dependency property sets the value indicating whether to save the state persisted on loading the GroupBar. 

Use the below code snippet to set this property.


{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" Width="230" SaveOriginalState="True" Name="groupBar"> 
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
//Enable the save state property
groupBar.SaveOriginalState = true; 
{% endhighlight %}

{% endtabs %}

