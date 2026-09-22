---
layout: post
title: How to Check an Item on Init in WPF CheckListBox | Syncfusion®
description: This section describes how to check an item using the SelectedItems API of the Syncfusion WPF CheckListBox control when the control is being initialized.
platform: wpf
control: CheckListBox
documentation: ug
---

# How to Check an Item on Init in WPF CheckedListBox

To check the items when initiating the WPF CheckedListBox control, items need to be added to the `SelectedItems` collection. The following code illustrates this:

{% tabs %}
{% highlight c#%}

// Assuming the CheckListBox is named 'checkListBox' and contains items
this.checkListBox.SelectedItems.Add(this.checkListBox.Items[4]);

{%endhighlight%}
{% endtabs %}
