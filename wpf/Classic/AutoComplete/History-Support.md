---
layout: post
title: History-Support | AutoComplete | wpf | Syncfusion
description: history support
platform: wpf
control: AutoComplete
documentation: ug
---

# History Support

History support in AutoComplete means, reuse of the items which are already used in the AutoComplete textbox. AutoComplete allows you to enable this history support by setting the value of the [IsHistory](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~IsHistory.html) property to True. AutoComplete guides you to select an item from the list of items which are added to the history, by using the drop-down button to open the drop-down list.

## Using history support in an application 

Items can be added to the history using the [AddToHistory(String string)](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~AddHistory(String).html) and [AddToHistory(Object obj)](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~AddHistory(Object).html) methods, only if that items are present in the data source used with the AutoComplete. Also it supports to save the history while closing the application and to load the history while opening the application using the [SaveHistory()](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~SaveHistory.html) and [LoadHistory()](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~LoadHistory.html) methods. 

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

[AddHistory(String)](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~AddHistory(String).html)
[AddHistory(Object)](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~AddHistory(Object).html)
[SaveHistory](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~SaveHistory.html)
[LoadHistory](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~LoadHistory.html)
[ClearAllHistory](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.AutoComplete~ClearAllHistory.html)

## Sample link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo
