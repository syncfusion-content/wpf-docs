---
layout: post
title: Item Selection | CheckListBox | wpf | Syncfusion
description: Learn here about Item Selection in Syncfusion Essential Studio WPF CheckListBox control, its elements and more.
platform: wpf
control: CheckListBox
documentation: ug
---

# Item Selection in WPF CheckListBox Control

In `CheckListBox`, checking of an item can be done with a single click using the [IsCheckOnFirstClick](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CheckListBox.html#Syncfusion_Windows_Tools_Controls_CheckListBox_IsCheckOnFirstClick) property. If this property is set to `false`, the item is checked only when a double click is detected. By default, the value of this property is `True`.

Here is the code for setting this property.

{% tabs %}
{%highlight xaml%}

<!-- Adding CheckListBox -->
<syncfusion:CheckListBox Name="checkListBox" IsCheckOnFirstClick="True"> 
<!-- Adding CheckListBox items -->  
<syncfusion:CheckListBoxItem Content="Mexico"/>
<syncfusion:CheckListBoxItem Content="Canada" /> 
<syncfusion:CheckListBoxItem Content="Bermuda" /> 
<syncfusion:CheckListBoxItem Content="Belize" />  
<syncfusion:CheckListBoxItem Content="Panama" />
</syncfusion:CheckListBox>
  
{%endhighlight%}

{%highlight c#%}

// Enable the IsCheckOnFirstClick property.
checkListBox.IsCheckOnFirstClick = true;

{%endhighlight%}
{% endtabs %}

![Item selection property](Item-Selection_images/Item-Selection_img1.jpeg)

IsCheckOnFirstClick = "True"
{:.caption}