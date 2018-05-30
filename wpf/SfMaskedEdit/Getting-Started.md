---
layout: post
title: Getting Started| SfMaskedEdit | Wpf | Syncfusion
description: getting started
platform: wpf
control: SfMaskedEdit
documentation: ug
---

# Getting Started

## Assembly Deployment

Namespace : Syncfusion.Windows.Controls.Input

Assembly: Syncfusion.SfInput.WPF

Dependent assembly: Syncfusion.SfShared.WPF

## Adding control via Designer

Create a new WPF application in the Visual Studio and follow the steps given.

1. Drag and drop the `SfMaskedEdit` control from the toolbox to the designer. It generates the `SfMaskedEdit` as shown:

![](Getting-Started_images/Getting-Started_img1.png)

## Adding control manually in XAML

The following code example shows how to create the `SfMaskedEdit` from XAML.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit Width="255" Height="46"/>

{% endhighlight %}

{% endtabs %}


## Adding control manually in CSharp

To create a MaskedEdit control, use the following code.

{% tabs %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit() { Text = "SfMaskedEdit", Width = 150, Height = 50 };
this.Content = maskededit;

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img2.jpg)

## Adding Mask to the control

To mask the input of SfMaskedEdit,  we must set `MaskType` and `Mask` property.

`MaskType` has different set of mask characters that are combined to form a mask expression. Based on the complexity and usage, mask types are classified as Simple, Regular and RegEx.

Using the `Mask` property, you can specify input without writing any custom validation logic in your application. Mask can be set based on `MaskType` elements. The `Mask` property may contain literals and special mask characters. You can use the back-slash character to escape any special mask characters so that they are displayed as literals.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000" Width="255" Height="46"/>
{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType=MaskType.Simple;
maskedEdit.Mask="00/00/0000";

{% endhighlight %}

{% endtabs %}


This mask expression allows only numeric inputs in the places of 0.

## Assigning Value to the control

By default, the Value holds the characters without including the prompt characters and the literals defined in the mask. You can alter this and allow the value to hold also literal and prompt characters by setting the ValueMaskFormat property of the control.

To set the value for the control, `Value` property can be used as follows:

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000" Value="14/11/2014" Width="255" Height="46"/>

{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType=MaskType.Simple;
maskedEdit.Mask="00/00/0000";
maskedEdit.Value="14/11/2014";

{% endhighlight %}

{% endtabs %}

## Defining Watermark

`Watermark`  allows you to give guidance to the end user on what should be enter in the text input. It can be displayed when the content of SfMaskedEdit is empty and the control is not focused.

To set the watermark for the control, `WaterMark` property can be used as follows:

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit  MaskType="Simple" Mask="00/00/0000" Watermark="Type here" Width="255" Height="46"/>

{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType = MaskType.Simple;
maskedEdit.Mask = "00/00/0000";
maskedEdit.Watermark = "Type here";

{% endhighlight %}

{% endtabs %}