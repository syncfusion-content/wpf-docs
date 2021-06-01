---
layout: post
title: Closing the GroupBar in Stack Mode in WPF Navigation Pane | Syncfusion
description: Learn here all about Closing the GroupBar in Stack Mode support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: Navigation Pane
documentation: ug
---

# Closing the GroupBar in Stack Mode in WPF Navigation Pane (GroupBar)

You can close the GroupBar in stack mode by enabling the close button. This is done by using the IsCloseButtonEnabled property. This dependency property sets the value indicating whether the close button is visible on the header of the item in stack mode when IsToolBarEnabled property is set to _false_. That is close button is visible only if toolbar is disabled. This property can work only in stack mode.

Use the below code snippet to set this property. 


{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" Width="230" IsCloseButtonEnabled="True" 	IsToolBarEnabled="False" VisualMode="StackMode" Name="groupBar">  
<!-- Adding GroupBarItem -->  
<syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True">  
  <!-- Adding content for groupbar item using panel -->   
  <StackPanel Orientation="Vertical">    
  <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>    
  <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton> 
  <RadioButton Margin="4,2,2,2"  >Vertical</RadioButton>   
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
//Setting the visual mode as stack mode
groupBar.VisualMode = VisualMode.StackMode;
//Enabling the close button
groupBar.IsCloseButtonEnabled = true;
//Disabling the toolbargroupBar.IsToolBarEnabled = false;
{% endhighlight %}
{% endtabs %}

## Maximum number of Visible Items in OverFlowPanel

User can customize the maximum number of Visible Items to be displayed in the StackMode OverflowPanel, using the property StackVisibleItemsCount. 

{% tabs %}
{% highlight xaml %}

<syncfusion:GroupBar Name="GroupBar" Height="340" VerticalAlignment="Center"
HorizontalAlignment="Center" VisualMode="StackMode" IsToolBarEnabled="True" StackVisibleItemsCount="2">
<syncfusion:GroupBarItem x:Name="groupitem1" HeaderText="Mail" HeaderImageSource="Images/mail.png"    >
<Border >
<TextBlock Text="GroupBarItem1" />
</Border>
</syncfusion:GroupBarItem>
<syncfusion:GroupBarItem HeaderText="Inbox" HeaderImageSource="Images/inbox.png" >
<Border >
<TextBlock Text="GroupBarItem2" />
</Border>
</syncfusion:GroupBarItem>
<syncfusion:GroupBarItem HeaderText="Notes" HeaderImageSource="Images/Notes.png"  >
<Border >
<TextBlock Text="GroupBarItem3" />
</Border>
</syncfusion:GroupBarItem>
<syncfusion:GroupBarItem HeaderText="Sent" HeaderImageSource="Images/sent.png" >
<Border >
<TextBlock Text="GroupBarItem4" />
</Border>
</syncfusion:GroupBarItem>
</syncfusion:GroupBar>

{% endhighlight %}

{% highlight C# %}
GroupBar.StackVisibleItemsCount = 2;
{% endhighlight %}
{% endtabs %}

![Maximum Number of Visible Items of WPF navigation pane](GroupBar_StackMode_images/Maximumnumberofvisibleitems.png)

Note: This property is applicable for SfSkinManager Office2016 themes. 
