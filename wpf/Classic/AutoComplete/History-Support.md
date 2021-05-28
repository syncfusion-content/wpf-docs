---
layout: post
title: History Support in WPF AutoComplete Control | Syncfusion
description: Learn here all about History Support in Syncfusion WPF AutoComplete (Classic) control, its elements and more details.
platform: wpf
control: AutoComplete
documentation: ug
---

# History Support in WPF AutoComplete (Classic)

History support in AutoComplete means, reuse of the items which are already used in the AutoComplete textbox. AutoComplete allows you to enable this history support by setting the value of the [IsHistory](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_IsHistory) property to True. AutoComplete guides you to select an item from the list of items which are added to the history, by using the drop-down button to open the drop-down list.

## Using history support in an application 

Items can be added to the history using the [AddToHistory(String string)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_AddHistory_System_String_) and [AddToHistory(Object obj)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_AddHistory_System_Object_) methods, only if that items are present in the data source used with the AutoComplete. Also it supports to save the history while closing the application and to load the history while opening the application using the [SaveHistory()](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SaveHistory) and [LoadHistory()](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_LoadHistory) methods. 

The following mentioned code example can be used to attain these functionalities.

{% tabs %}
{% highlight c# %}

AutoComplete autoComplete1 = new AutoComplete();
autoComplete1.Loaded += new RoutedEventHandler
(autoComplete1_Loaded);
void autoComplete1_Loaded(object sender, RoutedEventArgs e)
{
    if (autoComplete1!= null)
    autoComplete1.LoadHistory();
}

autoComplete1.SelectionChanged += new SelectionChangedEventHandler(autoComplete1_SelectionChanged);
private void autoComplete1_SelectionChanged(object sender, SelectionChangedEventArgs e)
{
    autoComplete1.AddHistory(autoComplete1.SelectedItem);
    autoComplete1.SaveHistory();
}

{% endhighlight %}
{% endtabs %}

## Tables for methods, and events

### Methods

[AddHistory(String)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_AddHistory_System_String_)
[AddHistory(Object)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_AddHistory_System_Object_)
[SaveHistory](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SaveHistory)
[LoadHistory](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_LoadHistory)
[ClearAllHistory](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_ClearAllHistory)

## Sample link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo
