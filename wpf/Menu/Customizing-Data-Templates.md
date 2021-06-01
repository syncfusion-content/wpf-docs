---
layout: post
title: Customizing Data Templates in WPF Menu control | Syncfusion
description: Learn here all about Customizing Data Templates support in Syncfusion WPF Menu (MenuAdv) control and more.
platform: wpf
control: MenuAdv
documentation: ug
---

# Customizing Data Templates in WPF Menu (MenuAdv)

Data templates can be customized for items of the MenuAdv control. The next section explains how to customize the MenuItemAdv using data templates.

## Item Template 

You can customize how a business object is displayed as MenuItemAdv using ItemTemplate of MenuAdv. The MenuAdv displays hierarchical data. HierarchicalDataTemplate is used to define the ItemTemplate. The following code example shows the usage of ItemTemplate.

{% highlight xaml %}




<syncfusion:MenuAdv ItemsSource="{Binding MenuItems}" >



<syncfusion:MenuAdv.ItemTemplate>



<HierarchicalDataTemplate ItemsSource="{Binding SubItems}">

<StackPanel Orientation="Horizontal">

<Image Source="App.ico"  Width="15" Height="15"/>

<TextBlock Text="{Binding Header}" FontWeight="Bold" 			FontStyle="Italic" />

</StackPanel>

</HierarchicalDataTemplate>



</syncfusion:MenuAdv.ItemTemplate>



</syncfusion:MenuAdv>


{% endhighlight %}


N> [View sample in GitHub](https://github.com/SyncfusionExamples/customizing-data-templates-in-menuadv)


Implementing the above code will generate the following MenuAdv control.

![Image showing the menu with ItemTemplate](Customizing-Data-Templates_images/Customizing-Data-Templates_img1.png)



