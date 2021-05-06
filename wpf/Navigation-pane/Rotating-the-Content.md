---
layout: post
title: Rotating the Content in WPF Navigation Pane control | Syncfusion
description: Learn here all about Rotating the Content support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: Navigation Pane
documentation: ug
---

# Rotating the Content in WPF Navigation Pane (GroupBar)

The position of the content can be changed by setting an angle to the ContentRotationAngle property. This dependency property sets the angle of rotation for displaying item contents. 

The following code snippet will help you setting this property.



{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar -->
<syncfusion:GroupBar Height="200" ContentRotationAngle="45" Width="230" Name="groupBar"> 
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem">    
 <!-- Adding content for groupbar item using panel -->  
 <StackPanel Orientation="Vertical">    
 <TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/>  
 <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal
 </RadioButton>    
 <RadioButton Margin="4,2,2,2">Vertical</RadioButton> 
 <TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/> 
 <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>  
 <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>   
 </StackPanel>  
 </syncfusion:GroupBarItem>
 </syncfusion:GroupBar>
 {% endhighlight %}

{% highlight C# %}
//Setting the rotation angle as 45
groupBar.ContentRotationAngle = 45; 
{% endhighlight %}
{% endtabs %}


{% seealso %}

Rotating the GroupBar

{% endseealso %}
