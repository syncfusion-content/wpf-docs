---
layout: post
title: How to Check an Item on Init in WPF CheckedListBox | Syncfusion
description: This section describes how to check an item using the SelectedItems API of the Syncfusion WPF CheckedListBox control when the control is being initialized.
platform: wpf
control: CheckListBox
documentation: ug
---

# How to Check an Item on Init in WPF CheckedListBox

To check the items when initiating the CheckListBox control, items need to be added in the SelectedItems collection._ The following code illustrates this:

{% tabs %}
{% highlight c#%}

this.ListBox.SelectedItems.Add(this.ListBox.Items[4]);

{%endhighlight%}
{% endtabs %}
