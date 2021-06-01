---
layout: post
title: Handling Selection in WPF Navigation Drawer control | Syncfusion
description: Learn here all about Handling Selection support in Syncfusion WPF Navigation Drawer (SfNavigationDrawer) control and more.
platform: WPF
control: NavigationDrawer
 documentation: ug
---

# Handling Selection in WPF Navigation Drawer (SfNavigationDrawer)

This section explains the handling of selection in SfNavigationDrawer. 

The [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_SelectedItem) property is used for getting or setting the currently selected item of the Navigation Drawer. There are two cases in accessing the SelectedItem property.

The first is when the Navigation Drawer is populated with NavigationItems, then the  SelectedItem property is of type NavigationItem.

{% tabs %}

{% highlight c# %}

var selectedItem = this.navigationDrawer.SelectedItem as NavigationItem;

{% endhighlight %}

{% endtabs %}

The other one is when the Navigation Drawer is bound to a collection of custom objects, the SelectedItem is of the type of the custom object.

{% tabs %}

{% highlight c# %}

var selectedItem = this.navigationDrawer.SelectedItem as NavigationModel;

{% endhighlight %}

{% endtabs %}


N> View [sample](https://github.com/SyncfusionExamples/wpf-sfnavigationdrawer-samples/tree/main/Handling_Selection) in GitHub
