---
layout: post
title: Basic Core Features in WPF AutoComplete Control | Syncfusion
description: Learn here all about Basic Core Features support in Syncfusion WPF AutoComplete (Classic) control and more.
platform: wpf
control: AutoComplete
documentation: ug
---

# Basic Core Features in WPF AutoComplete (Classic)

AutoComplete supports basic core features which are listed as follows.

* [SelectedIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectedIndex)— Used to set and get the index of the selected item.
* [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectedItem)—Used to get which item of the AutoComplete has been selected.
* [SelectedValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectedValue)—Used to get the value of the selected item, the value of the SelectedValue property will be set based on the value of the SelectedValuePath property.
* [SelectedValuePath](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectedValuePath)—Used to set the value of the SelectedValue property of the AutoComplete.
* [DisplayMemberPath](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.displaymemberpath?view=netframework-4.7.2)—Used to set the value for the items displayed in the drop-down list.
* [IsDropDownOpen](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_IsDropDownOpen)—Used to open or close the Drop-down list by setting its value as True or False.
* [SelectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html).
* [TextChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html).

## Using basic core features in an application

In the [SelectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html) event the [SelectedIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectedIndex), [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectedItem) & [SelectedValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.AutoComplete.html#Syncfusion_Windows_Tools_Controls_AutoComplete_SelectedValue) properties can be used in the application to get these property values. The properties and events listed can be used in the application as mentioned below.

{% tabs %}
{% highlight c# %}

List<String> Products = new List<String>();

Products.Add("Diagram");
Products.Add("Gauge");
Products.Add("Chart");
Products.Add("Business Intelligence");

AutoComplete autoComplete1 = new AutoComplete();
autoComplete1.CustomSource = Products;
autoComplete1.SelectedIndex = 1;
autoComplete1.IsDropDownOpen = true;
autoComplete1.SelectionChanged += 

new SelectionChangedEventHandler(autoComplete1_SelectionChanged);
autoComplete1.TextChanged += new PropertyChangedCallback(autoComplete1_TextChanged);
void autoComplete1_TextChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    this.textBlock.Text = this.autoComplete1.Text;
}

void autoComplete1_SelectionChanged(object sender, SelectionChangedEventArgs e)
{
    MessageBox.Show("SelectedItem: " +
    this.autoComplete1.SelectedItem.ToString()+ "\n" + "SelectedValue: "
    + this.autoComplete1.SelectedValue.ToString())
}

{% endhighlight %}
{% endtabs %}

## Sample link

WPF Sample Browser-> Tools -> Editors -> AutoComplete Demo
