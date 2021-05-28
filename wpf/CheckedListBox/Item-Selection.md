---
layout: post
title: Item Selection | CheckListBox | wpf | Syncfusion
description: Learn here about Item Selection in Syncfusion Essential Studio WPF CheckListBox control, its elements and more.
platform: wpf
control: CheckListBox
documentation: ug
---

# Item Selection in WPF CheckListBox Control

In CheckListBox, selection of item can be done by single click using the property [IsCheckOnFirstClick](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.CheckListBox.html#Syncfusion_Windows_Tools_Controls_CheckListBox_IsCheckOnFirstClick). If it is false, then the selection is done when double click is detected. By default, the value of this property is “True”.

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
</syncfusion:CheckListBox></td></tr>
  
{%endhighlight%}

{%highlight c#%}

// Enable the IsCheckOnFirstClick property.
checkListBox.IsCheckOnFirstClick = true;  </td></tr>

{%endhighlight%}
{% endtabs %}

![Item selection property](Item-Selection_images/Item-Selection_img1.jpeg)

IsCheckOnFirstClick = "True"
{:.caption}