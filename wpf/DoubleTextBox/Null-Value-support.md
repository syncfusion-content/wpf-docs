---
layout: post
title: Null-Value-support
description: null value support
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Null Value support

DoubleTextBox accepts null values. To enable the null option you have to set the UseNullOption property to true. You can also set the NullValue property for the DoubleTextBox. When you set the null value to the Value property, by default the value of the NullValue (Default value is null)property will be assigned to the Value property. 



<table>
<tr>
<td>
XAML<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150"                             UseNullOption="True" NullValue="1"/></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new                           Syncfusion.Windows.Shared.DoubleTextBox();doubleTextBox.Width = 150;doubleTextBox.Height = 25;doubleTextBox.UseNullOption = true;doubleTextBox.NullValue = 1;</td></tr>
</table>


In this sample, the NullValue (NullValue = 1) is set to the Value property of the DoubleTextBox because the default value of the Value property is null.



{{ '![](Null-Value-support_images/Null-Value-support_img1.png)' | markdownify }}
{:.image }




<table>
<tr>
<td>
XAML<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150"                             UseNullOption="True" NullValue="{x:Null}"/></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new                            Syncfusion.Windows.Shared.DoubleTextBox();doubleTextBox.Width = 150;doubleTextBox.Height = 25;doubleTextBox.UseNullOption = true;doubleTextBox.NullValue = null;</td></tr>
</table>


In this sample, the NullValue (NullValue = null) is set to the Value property of the DoubleTextBox. (Default value of the Value property is null).



{{ '![](Null-Value-support_images/Null-Value-support_img2.png)' | markdownify }}
{:.image }


See Also

Maximum and Minimum Value

Watermark support

