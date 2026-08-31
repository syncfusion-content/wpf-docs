---
layout: post
title: Appearance in WPF TabNavigation | Syncfusion®
description: Appearance in WPF TabNavigation allows customization of tab styles, colors, and layouts to create visually appealing interfaces.
platform: wpf
control: TabNavigation
documentation: ug
---

# Appearance in WPF Tab Navigation

## Show/hide the Header

You can enable/disable the visibility of header by setting [HeaderVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabNavigationControl.html#Syncfusion_Windows_Tools_Controls_TabNavigationControl_HeaderVisibility) property of Tab Navigation Control.

{% tabs %}
{% highlight XAML %}
 <!-- Tab Navigation Control -->
<syncfusion:TabNavigationControl x:Name="TabNavigation" HeaderVisibility="Collapsed" >
	<syncfusion:TabNavigationItem Header="TabItem1" Content="TabNavigationItem 1"/>
	<syncfusion:TabNavigationItem Header="TabItem2" Content="TabNavigationItem 2"/>
	<syncfusion:TabNavigationItem Header="TabItem3" Content="TabNavigationItem 3"/>
</syncfusion:TabNavigationControl>
{% endhighlight %}
{% highlight C# %}
//Hide the header
tabNavigation.HeaderVisibility = Visibility.Collapsed;
{% endhighlight %}
{% endtabs %}

![wpf tab navigation header visible](Appearance_images/wpf-tab-navigation-header-visible.png)
![wpf tab navigation header collapsed](Appearance_images/wpf-tab-navigation-header-collapsed.png)

## Show/hide the NavigationButton

You can enable/disable the visibility of navigation button by setting [NavigationButtonVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabNavigationControl.html#Syncfusion_Windows_Tools_Controls_TabNavigationControl_NavigationButtonVisibility) property of Tab Navigation Control.

{% tabs %}
{% highlight XAML %}
<!-- Tab Navigation Control -->
<syncfusion:TabNavigationControl x:Name="TabNavigation" TabStripVisibility="Visible" NavigationButtonVisibility="Collapsed" >
	<syncfusion:TabNavigationItem Header="TabItem1" Content="TabNavigationItem 1"/>
	<syncfusion:TabNavigationItem Header="TabItem2" Content="TabNavigationItem 2"/>
</syncfusion:TabNavigationControl>
{% endhighlight %}
{% highlight C# %}
//Hide the navigation button
tabNavigation.NavigationButtonVisibility = Visibility.Collapsed;
{% endhighlight %}
{% endtabs %}

![wpf tab navigation button visible](Appearance_images/wpf-tabnavigation-navigation-button-visibility.png)

![wpf tab navigation button collapsed](Appearance_images/wpf-tabnavigation-navigation-button-collapsed.png)

## Show/hide the TabStrip

You can enable/disable the visibility of tab strip by setting [TabStripVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabNavigationControl.html#Syncfusion_Windows_Tools_Controls_TabNavigationControl_TabStripVisibility) property of Tab Navigation Control.

{% tabs %}
{% highlight XAML %}
<!-- Tab Navigation Control -->
<syncfusion:TabNavigationControl x:Name="TabNavigation" TabStripVisibility="Visible">
	<syncfusion:TabNavigationItem Header="TabItem1" Content="TabNavigationItem 1"/>
	<syncfusion:TabNavigationItem Header="TabItem2" Content="TabNavigationItem 2"/>
</syncfusion:TabNavigationControl>
{% endhighlight %}
{% highlight C# %}
//Enable the tab strip visibility
tabNavigation.TabStripVisibility = Visibility.Visible;
{% endhighlight %}
{% endtabs %}

![wpf tab navigation tab strip visible](Appearance_images/wpf-tabnavigation-tabstrip-button-visibility.png)

![wpf tab navigation tab strip collapsed](Appearance_images/wpf-tabnavigation-tabstrip-button-collapsed.png)
