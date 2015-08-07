---
layout: post
title: Getting-Started
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

{% highlight xml %}


[XAML]

xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

{% endhighlight %}



After adding the above namespace, the ComboBoxAdv can be added to the application as shown below:


{% highlight xml %}

[XAML]

    <syncfusion:ComboBoxAdv x:Name="comboBoxAdv1" AllowMultiSelect="True" 		DefaultText="Choose Items" ItemsSource="{Binding Countries}"                                	DisplayMemberPath="Name"  SelectedValuePath="Code"

      SelectedValueDelimiter=" - ">

    </syncfusion:ComboBoxAdv>
{% endhighlight %}




### Adding Through C#

To add ComboBoxAdv using C#, first include the following namespace in C#.


{% highlight c# %}


[C#]

using Syncfusion.Windows.Tools.Controls;

{% endhighlight %}



After adding the above namespace, the ComboBoxAdv can be added to the application as shown below:


{% highlight c# %}


[C#]

    ComboBoxAdv comboBoxAdv = new ComboBoxAdv { AllowMultiSelect = true, 	SelectedValueDelimiter = " - ", DefaultText = " Choose Itmes ", 	ItemsSource = Countries, DisplayMemberPath="Name", 	SelectedValuePath="Code" };

{% endhighlight %}



