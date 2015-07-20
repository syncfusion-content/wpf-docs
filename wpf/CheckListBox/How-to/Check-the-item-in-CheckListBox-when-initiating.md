---
layout: post
title: Check-the-item-in-CheckListBox-when-initiating
description: check the item in checklistbox when initiating? 
platform: wpf
control: CheckListBox
documentation: ug
---

### Check the item in CheckListBox when initiating? 

To check the items when initiating the CheckListBox control, use the IsSelected property of ItemContainerStyle_._ The following code illustrates this:__

[XAML]



&lt;syncfusion:CheckListBox.ItemContainerStyle&gt;

            &lt;Style TargetType="syncfusion:CheckListBoxItem"&gt;

                &lt;Setter Property="IsSelected" Value="{Binding IsChecked, Mode=TwoWay}"/&gt;

            &lt;/Style&gt;

&lt;/syncfusion:CheckListBox.ItemContainerStyle&gt;



