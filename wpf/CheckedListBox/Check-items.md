---
layout: post
title: Check items | CheckListBox | wpf | Syncfusion
description: This section describes about different ways available to check an item present in the CheckListBox control.
platform: wpf
control: CheckListBox
documentation: ug
---

# Check items

In CheckListBox,items present in the control can be checked either by using any one of the following ways:

1. Programmatically
2. Using mouse
3. Using keyboard

## Programmatically

The CheckListBox items can be checked programmatically by adding the items in SelectedItems collection.

{% tabs %}
{% highlight c#%}

this.ListBox.SelectedItems.Add(this.ListBox.Items[4]);

{%endhighlight%}
{% endtabs %}


## Using mouse

The CheckListBox items can be checked or unchecked in a single click either by clicking the checkbox or clicking the content of the item.  

## Using keyboard

Space key and Enter key allows the users to change the checked state of an item. Items can be checked or unchecked using these two keys.

Based on the checked state of a GroupHeader and SelectAll item, their corresponding child items will be updated and vice versa.

 