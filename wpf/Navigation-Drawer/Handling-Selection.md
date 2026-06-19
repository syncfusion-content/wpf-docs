---
layout: post
title: Handling Selection in WPF Navigation Drawer Control | Syncfusion®
description: Learn about handling selection support in the Syncfusion® WPF Navigation Drawer (SfNavigationDrawer) control.
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Handling Selection in WPF Navigation Drawer (SfNavigationDrawer)

This section explains how to handle selection in the SfNavigationDrawer.

The [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_SelectedItem) property is used to get or set the currently selected item of the Navigation Drawer. There are two scenarios when accessing the `SelectedItem` property:

1. When the Navigation Drawer is populated with `NavigationItems`, the `SelectedItem` property is of type `NavigationItem`.

{% tabs %}

{% highlight c# %}

var selectedItem = this.navigationDrawer.SelectedItem as NavigationItem;

{% endhighlight %}

{% endtabs %}

2. When the Navigation Drawer is bound to a collection of custom objects, the `SelectedItem` is of the type of the custom object.

{% tabs %}

{% highlight c# %}

var selectedItem = this.navigationDrawer.SelectedItem as NavigationModel;

{% endhighlight %}

{% endtabs %}

> **Note:** View the [sample](https://github.com/SyncfusionExamples/wpf-sfnavigationdrawer-samples/tree/main/Handling_Selection) on GitHub.
