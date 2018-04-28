---
layout: post
title: Check the item in CheckListBox when initiating | CheckListBox | wpf | Syncfusion
description: check the item in checklistbox when initiating? 
platform: wpf
control: CheckListBox
documentation: ug
---

# Check the Item in CheckListBox when Initiating

To check the items when initiating the CheckListBox control, use the IsSelected property of ItemContainerStyle_._ The following code illustrates this:

{% tabs %}
{% highlight xaml %}

<syncfusion:CheckListBox.ItemContainerStyle>
<Style TargetType="syncfusion:CheckListBoxItem">
<Setter Property="IsSelected" Value="{Binding IsChecked, Mode=TwoWay}"/>
</Style>
</syncfusion:CheckListBox.ItemContainerStyle>

{% endhighlight  %}
{% endtabs %}
