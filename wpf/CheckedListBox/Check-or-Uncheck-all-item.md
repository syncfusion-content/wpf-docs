---
layout: post
title: Check or Uncheck all item | CheckListBox | wpf | Syncfusion
description: This section describes how to check or uncheck all the Checklistbox items present in the CheckListBox using SelectAll property.
platform: wpf
control: CheckListBox
documentation: ug
---

# Check or Uncheck all item

In CheckListBox, the SelectAll option can be enabled or disabled using the [IsSelectAllEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.CheckListBox~IsSelectAllEnabled.html) property. The SelectAll option allows the users to check or uncheck all the items in the list with a single click. Selection mode of the SelectAll item varies based on the checked state of the CheckListBox items.


{% tabs %}
{%highlight xaml%}

  <syncfusion:CheckListBox 
		        x:Name="checkListBox"
		        Width="300" 
			      Height="400"
            HorizontalAlignment="Center" 
            VerticalAlignment="Center"
            Margin="10"
            ItemsSource="{Binding GetModels}"
            IsSelectAllEnabled="True">
</syncfusion:CheckListBox>

{%endhighlight%}

{% highlight c#%}

// SelectAll option enabled for CheckListBox

checkListBox.IsSelectAllEnabled = true;

{%endhighlight%}
{% endtabs %}

![Select All item in CheckListBox](Select-All_images/select_all.png)