---
layout: post
title: Check or Uncheck All Items in WPF CheckListBox | Syncfusion®
description: Select or clear every item at once in the Syncfusion WPF CheckListBox control using the built-in Select All and Uncheck All support.
platform: wpf
control: CheckListBox
documentation: ug
---

# Check or Uncheck All Items in WPF CheckListBox

The [CheckListBox](https://www.syncfusion.com/wpf-ui-controls/CheckedListBox) allows users to check or uncheck all the items with a single click on the `SelectAll` option. The `SelectAll` option can be enabled or disabled using the [IsSelectAllEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CheckListBox.html#Syncfusion_Windows_Tools_Controls_CheckListBox_IsSelectAllEnabled) property. The selection state of the `SelectAll` item varies based on the checked state of the `CheckListBox` items. Initially, `SelectAll` is unchecked because no items are checked. It is checked only when all items are checked; otherwise, it is in an intermediate state.

{% tabs %}
{%highlight C#%}
 
//ViewModel.cs

class ViewModel { 
    public ObservableCollection<string> DaysCollection { get; set; }

    public ViewModel() {
        //Days added in the collection
        DaysCollection = new ObservableCollection<string>();
        DaysCollection.Add("Sunday");
        DaysCollection.Add("Monday");
        DaysCollection.Add("Tuesday");
        DaysCollection.Add("Wednesday");
        DaysCollection.Add("Thursday");
        DaysCollection.Add("Friday");
        DaysCollection.Add("Saturday");
    }
}

{%endhighlight%}
{% endtabs %}

{% tabs %}
{%highlight xaml%}

<syncfusion:CheckListBox IsSelectAllEnabled="False"
                         ItemsSource="{Binding DaysCollection}"                 
                         Name="checkListBox">
    <syncfusion:CheckListBox.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:CheckListBox.DataContext>
</syncfusion:CheckListBox>

{%endhighlight%}
{%highlight C#%}

CheckListBox checkListBox = new CheckListBox();
checkListBox.DataContext = new ViewModel();
checkListBox.ItemsSource = (checkListBox.DataContext as ViewModel).DaysCollection;

{%endhighlight%}
{% endtabs %}

![CheckListBox items are selected using the SelectAll option](Select-All_images/select_all.png)

Click [here](https://github.com/SyncfusionExamples/wpf-checked-listbox-examples/tree/master/Samples/SelectAll) to download the sample that showcases the SelectAll option in the `CheckListBox`.
