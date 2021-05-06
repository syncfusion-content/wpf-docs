---
layout: post
title: Setting Animation for GroupBar expansioncollapse in WPF Navigation Pane control | Syncfusion
description: Learn here all about Setting Animation for GroupBar expansioncollapse support in Syncfusion WPF Navigation Pane (GroupBar) control and more.
platform: wpf
control: GroupBar
documentation: ug
---

# Setting Animation for GroupBar expansioncollapse in WPF Navigation Pane (GroupBar)

## Animation Speed

The expanding and collapsing operation in a GroupBar leads to an animated action. This animation is controlled using the AnimationSpeed property, which sets the speed of animation. This dependency property will be activated when the user expands or collapses the GroupBar Item of the GroupBar control. Using this property, you can control the animation speed of GroupBarItem while expanding / collapsing. It returns the speed of animation.

Use the following code snippet to set this property.


{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar that have animation speed -->
<syncfusion:GroupBar Height="300" Width="230" Name="groupBar" AnimationSpeed="5" AnimationType="Fade"> 
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"> 
 <!-- Adding content for GroupBar item using GroupView -->   
 <syncfusion:GroupView Name="groupView" IsListViewMode="True">  
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
 <!-- Adding GroupBarItem --> 
 <syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence">  
 <!-- Adding content for GroupBar item using GroupView -->    
 <syncfusion:GroupView>   
 <syncfusion:GroupViewItem Text="Save State"/>   
 <syncfusion:GroupViewItem Text="Load State"/> 
 <syncfusion:GroupViewItem Text="Reset State"/>
 </syncfusion:GroupView>
 </syncfusion:GroupBarItem>
 </syncfusion:GroupBar>
 {% endhighlight %}

{% highlight C# %}
//Getting the speed of animation
groupBar.AnimationSpeed = 5; 
{% endhighlight %} 
{% endtabs %}


## Animation Type

When the GroupBar is collapsed or expanded, it gives an animation effect. There are three types of animation, defined for the GroupBar control using AnimationType property. This dependency property sets the animation type to be applied when GroupBar is collapsed or expanded. It provides the following options.

* Fade - Animation fades out when the GroupBar is collapsed or expanded
* None - No animation when the GroupBar is collapsed or expanded
* Slide - Animation slides when the GroupBar is collapsed or expanded

Use the following code snippet to set AnimationType property.

{% tabs %}
{% highlight xaml %}
<!-- Adding GroupBar that have AnimationType as Fade -->
<syncfusion:GroupBar Height="300" Width="230" AnimationType="Fade" Name="groupBar">
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
  <!-- Adding GroupBarItem --> 
  <syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence">  
  <!-- Adding content for GroupBar item using GroupView -->  
  <syncfusion:GroupView>   
  <syncfusion:GroupViewItem Text="Save State"/>  
  <syncfusion:GroupViewItem Text="Load State"/>  
  <syncfusion:GroupViewItem Text="Reset State"/> 
  </syncfusion:GroupView> 
  </syncfusion:GroupBarItem>
  </syncfusion:GroupBar>{% endhighlight %}

{% highlight C# %}
//To set animation type as Fade
groupBar.AnimationType = AnimationsType.Fade;
//To set animation type as None
groupBar.AnimationType = AnimationsType.None;
//To set animation type as Slide
groupBar.AnimationType = AnimationsType.Slide;
{% endhighlight %}
{% endtabs %}


