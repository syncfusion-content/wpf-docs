---
layout: post
title: Getting Started | YoucancustomizetheappearanceoftheComboBoxAdvcontrolbyeditingthestyleofthecontrolinExpressionBlendorbyusingthefollowingpropertiesexposedbyComboBoxAdv | wpf | Syncfusion
description: getting started
platform: wpf
control: ComboBoxAdv
documentation: ug
---

# Getting Started

## Feature Summary

The features of the ComboBoxAdv control are listed below:

* AllowMultiSelect—ComboBoxAdv allows multiple selection
* DefaultText—ComboBoxAdv displays a string when none of the items is selected 
* SelectedValueDelimiter—It allows customizing the delimiter string displayed between selected items

## Adding ComboBoxAdv to an Application


The ComboBoxAdv control is available in the following assembly: 

Syncfusion.Shared.Wpf.dll

After adding reference to the above assembly, the control can be added to the application in the following ways. 

### Adding Through XAML

To add ComboBoxAdv using XAML, first include the following namespace in the XAML.

{% highlight xaml %}




xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

{% endhighlight %}



After adding the above namespace, the ComboBoxAdv can be added to the application as shown below:


{% highlight xaml %}



    <syncfusion:ComboBoxAdv x:Name="comboBoxAdv1" DefaultText="Choose Items" ItemsSource="{Binding Countries}"                                	DisplayMemberPath="Name"  SelectedValuePath="Code"

      SelectedValueDelimiter=" - ">

    </syncfusion:ComboBoxAdv>

{% endhighlight %}




### Adding Through C#

To add ComboBoxAdv using C#, first include the following namespace in C#.


{% highlight c# %}




using Syncfusion.Windows.Tools.Controls;

{% endhighlight %}



After adding the above namespace, the ComboBoxAdv can be added to the application as shown below:


{% highlight c# %}




    ComboBoxAdv comboBoxAdv = new ComboBoxAdv {SelectedValueDelimiter = " - ", DefaultText = " Choose Items ", ItemsSource = Countries, DisplayMemberPath="Name", 	SelectedValuePath="Code" };

{% endhighlight %}


## Use Case Scenarios

If multiple choices are allowed for the user, then the ComboBoxAdv is useful to display those multiple choices. Instead of displaying all the choices initially,the choices displayed with in the drop-down whenever the user click on the ComboBoxAdv control.

## Default Selection Behavior

By default, `AllowMultiSelect` property of ComboboxAdv is false. Therefore, it allows users to select only one item from drop-down. In default selection, previous selection has been cleared when new item is selected.

The following screenshot displays the default selection behavior of ComboBoxAdv.



![](ComboBoxAdv_images/ComboBoxAdv_img1.png)


