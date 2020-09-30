---
layout: post
title: Selection-Mode-Support | AutoComplete | wpf | Syncfusion
description: selection mode support
platform: wpf
control: AutoComplete
documentation: ug
---

# Selection Mode Support

AutoComplete supports two kinds of Selection Mode namely Single and Multiple. You can select the Mode using the [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectionMode) property. 

When the [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectionMode) property is set as Single, only one item can be selected at a time. The following image illustrates the Single selection mode.

![selection mode support](Selection-Mode-Support_images/Selection-Mode-Support_img1.png)

SelectionMode-Single
{:.caption}

When the [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectionMode) is set as Multiple, you can select multiple items by using the [SeparatorChar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SeparatorChar) property to separate the selected items. By default the SeparatorChar is “;”. This allows you to select multiple items by using the [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectionMode) property. Once an item is selected the [SeparatorChar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SeparatorChar) is to be entered in the text box to select the next item.

The following image illustrates the Multiple selection mode.

![selection mode support](Selection-Mode-Support_images/Selection-Mode-Support_img2.png)

SelectionMode—Multiple
{:.caption}

When the [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectionMode) is set as Extended, you can select multiple items at a time by pressing the Ctrl key. While selecting the multiple items, the selected items will be separated by the [SeparatorChar](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SeparatorChar) automatically.

The following image illustrates the Multiple selection mode.

![selection mode support](Selection-Mode-Support_images/Selection-Mode-Support_img3.png)

SelectionMode—Extended
{:.caption}

Adding Single, Multiple & Extended Selection Support to an Application 

The [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectionMode) property is used to attain these functionalities by setting its value as Single or Multiple or Extended. By default its value is Single. The following code snippet is used to set the [SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectionMode) property. 

{% tabs %}
{% highlight xaml %}

<syncfusion:AutoComplete x:Name="AutoComplete2" SelectionMode="Multiple"/>

{% endhighlight %}
{% highlight c# %}

AutoComplete autoComplete1 = new AutoComplete();this.autoComplete2.SelectionMode = SelectionMode.Multiple;

{% endhighlight %}
{% endtabs %}

## Tables for properties and events

### Events

* [SelectionModeChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html)

## Sample link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo
