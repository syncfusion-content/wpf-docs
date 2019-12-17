---
layout: post
title: Selection changed notification | CheckListBox | wpf | Syncfusion
description: This section describes about Selection changed event and how event could be handled using SelectionChangedEventArgs in CheckListBox control.
platform: wpf
control: CheckListBox
documentation: ug
---

# Selection changed notification

The [SelectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.CheckListBox~SelectionChanged_EV.html) event is raised while selecting an item at the execution time.The [SelectionChangedEventArgs](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.selectionchangedeventargs?redirectedfrom=MSDN&view=netframework-4.8) has the following members that provides information for the SelectionChanging event:

* Added items : Gets a collection of the underlying data objects in which the selection has to be processed.
* Removed items : Gets a collection of the underlying data objects in which the selection has to be removed.

{% tabs %}
{% highlight XAML %}
<syncfusion:CheckListBox x:Name="checkListBox" Width="120" Height="150" DisplayMemberPath="Name" ItemsSource="{Binding CheckListItems}" SelectionChanged="ListBox_SelectionChanged"/>
{% endhighlight %}
{% highlight C# %}

private void ListBox_SelectionChanged(object sender, SelectionChangedEventArgs e)
{
    Console.WriteLine("SelectionChanged event is raised");
}

{% endhighlight %}
{% endtabs %}