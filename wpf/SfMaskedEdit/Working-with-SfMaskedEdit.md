---
layout: post
title: Working With SfMaskedEdit| SfMaskedEdit | Wpf | Syncfusion
description: Working With SfMaskedEdit
platform: wpf
control: SfMaskedEdit
documentation: ug
---

#  Working With SfMaskedEdit

This section explains about accessing `SfMaskedEdit` properties and events associated with it.

## Masking the Input

The Mask property may contain literals and special mask characters. You can use the back-slash character to escape any special mask characters so that they are displayed as literals. Mask can be set based on MaskType elements

For Masking the input set MaskType and Mask property as follows:

<table>
<tr>
<th>
Type</th><th>
MaskType</th><th>
Mask</th></tr>
<tr>
<td>
Date</td><td>
Simple</td><td>
00/00/0000</td></tr>
<tr>
<td>
Phone </td><td>
Regular</td><td>
(d{3})-\d{3}-\d{4}</td></tr>
<tr>
<td>
Email</td><td>
RegEx</td><td>
[A-Za-z0-9._%-]+@[A-Za-z0-9]+\.[A-Za-z]{2,3}</td></tr>
</table>

### Simple Mask

If MaskType set as Simple, Mask can be created using Simple Mask Elements

Example: Date

Mask = "00/00/0000";

In the above example, we can create Mask for Date  ("dd/mm/yyyy") format. It will accept only digits. So that element ‘0’ is used and the literal ‘/’ is used.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000" Width="255" Height="46"/>
{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType=MaskType.Simple;
maskedEdit.Mask="00/00/0000";

{% endhighlight %}

{% endtabs %}

![](MaskOptions_images/mask_option_image1.jpg)

![](MaskOptions_images/mask_option_image2.jpg)

### Regular Mask

If MaskType set as Regular, Mask can be created using Regular Mask Elements

Example: Phone Number

Mask = "(d{3})-\d{3}-\d{4}"

In the above example, we can create a mask for Phone Number("(123)-456-7890"). It will accept only digits. So that element ‘d’ is used. Mobile Number has fixed size. So that element ‘{}’ is used and the literal ‘()’ and ‘-‘ is used.


{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit MaskType="Regular" Mask="(\d{0,3})\d{3}-\d{2}-\d{2}" Width="255" Height="46"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType = MaskType.Regular;
maskedEdit.Mask = "(\d{0,3})\d{3}-\d{2}-\d{2}";

{% endhighlight %}

{% endtabs %}

![](Working_with_SfMaskedEdit_images/Working_with_SfMaskedEdit_img1.jpg)

![](Working_with_SfMaskedEdit_images/Working_with_SfMaskedEdit_img2.jpg)

### RegEx Mask

If MaskType set as RegEx, Mask can be created using RegEx Mask Elements

Example : Email ID

Mask ="[A-Za-z0-9._%-]+@[A-Za-z0-9]+\.[A-Za-z]{2,3}"

In the above example, we can create a mask for Mail ID. It will accept both alphabets and digits. So that element ‘A-Za-z0-9’ is used. For accepting any number of characters  element ‘[ ]’ is used and the literal ‘@’ and ‘.’ is used.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit MaskType="RegEx" Mask="[A-Za-z0-9._%-]+@[A-Za-z0-9]+.[A-Za-z]{2,3}" Width="255" Height="46"/>
{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType = MaskType.RegEx;
maskedEdit.Mask = "[A-Za-z0-9._%-]+@[A-Za-z0-9]+.[A-Za-z]{2,3}";

{% endhighlight %}

{% endtabs %}

![](MaskOptions_images/mask_option_image5.jpg)

## Binding Value

The `SfMaskedEdit` control displays the value that can be set using the `Value` property:

### Set the Value property directly

The following example shows how to set the `Value` directly in `SfMaskedEdit`

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000"  Value="14/11/2014" Width="255" Height="46"/>
{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType = MaskType.Simple;
maskedEdit.Mask = "00/00/0000";
maskedEdit.Value = "14/11/2014";

{% endhighlight %}

{% endtabs %}

![](Working_with_SfMaskedEdit_images/Working_with_SfMaskedEdit_img3.jpg)

### Set the value property through binding

The following example shows Set the value property in ComboBox items to bind the `Value` property of the control


{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000"  Value="{Binding ElementName=comboBox, Path=Text}"  Width="255" Height="46"/>

{% endhighlight %}

{% endtabs %}

## ValueChanged event

Occurs when the value of the `Value` property is changed by either entering the valid input character or setting the value to the `Value` property through XAML or C# code. The event arguments are of type `ValueChangedEventArgs` and expose the following property:

> Your valid input character is updated to `Value` property based on the `ValidationMode` property.
> Refer to this [link](validation.html#validation-mode) to know more about the `ValidationMode` property of `SfMaskedEdit` control.

### Example

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000"  Value="14/11/2014" Width="255" Height="46" ValueChanged="sfMaskedEdit_ValueChanged"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit sfmaskedEdit = new SfMaskedEdit();	
sfmaskedEdit.ValueChanged += SfMaskedEdit_ValueChanged;

private void SfMaskedEdit_ValueChanged(object sender, EventArgs e)
{
   MessageBox.Show("Value changed");
}

{% endhighlight %}

{% endtabs %}

## Watermark

The watermark will prompt you with instructions or important information when it is not on focus and any valid characters are not entered. The `Watermark` property of `SfMaskedEdit` is used to set the watermark text for the control.

### Example

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit  MaskType="Simple" Mask="00/00/0000" Watermark="Type here" Width="255" Height="46"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType = MaskType.Simple;
maskedEdit.Mask = "00/00/0000";
maskedEdit.Watermark = "Type here";

{% endhighlight %}

{% endtabs %}

![](Working_with_SfMaskedEdit_images/Working_with_SfMaskedEdit_img4.jpg)



