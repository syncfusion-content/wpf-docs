---
layout: post
title: Check the item in CheckListBox when initiating | CheckListBox | wpf | Syncfusion
description: check the item in checklistbox when initiating? 
platform: wpf
control: CheckListBox
documentation: ug
---

# Check the Item in CheckListBox when Initiating

To check the items when initiating the CheckListBox control, items need to be added in the SelectedItems collection._ The following code illustrates this:

{% tabs %}
{% highlight c#%}

this.ListBox.SelectedItems.Add(this.ListBox.Items[4]);

{%endhighlight%}
{% endtabs %}
