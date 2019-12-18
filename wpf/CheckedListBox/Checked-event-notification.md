---
layout: post
title: Checked event notification | CheckListBox | wpf | Syncfusion
description: This section describes about Checked event notification in CheckListBox control and how event event could be handled using ItemCheckedEventArgs.
platform: wpf
control: CheckListBox
documentation: ug
---

# Checked event notification

When the checked state of an item is changed,it will be notified using the [ItemChecked](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.checkedlistbox.itemcheck?view=netframework-4.8) event.The event handler has an argument of type ItemCheckedEventArgs containing data related to this event.

{% tabs %}
{% highlight XAML %}
<syncfusion:CheckListBox x:Name="checkListBox" Width="120" Height="150" DisplayMemberPath="Name" ItemsSource="{Binding CheckListItems}" ItemChecked="ListBox_ItemChecked"/>
{% endhighlight %}
{% highlight C# %}

private void ListBox_ItemChecked(object sender, ItemCheckedEventArgs e)
{
   Console.WriteLine("ItemChecked event is raised");
}

{% endhighlight %}
{% endtabs %}

A CheckListBoxItem can be checked in any of the following ways:

* Using keyboard
* Using mouse
* Programmatically