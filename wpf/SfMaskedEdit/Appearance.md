---
layout: post
title: Appearence | SfMaskedEdit | Wpf | Syncfusion
description: Appearence of SfMaskedEdit
platform: wpf
control: SfMaskedEdit
documentation: ug
---
# Appearence

The appearance of the `SfMaskedEdit` control can be customized by using the `BorderBrush` and `ErrorBorderBrush` property

## Border


### BorderBrush

`BorderBrush` provides the border color for the `SfMaskedEdit`.

We can Customize the `BorderBrush` property as follows

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit Width="255" Height="46" BorderBrush="Violet"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.BorderBrush = Brushes.Violet;

{% endhighlight %}

{% endtabs %}

![](Appearence_Images/Appearence_Img1.jpg)


### ErrorBorderBrush


`ErrorBorderBrush` provide the border color for the `SfMaskedEdit` when validation becomes failed.

We can Customize the ErrorBorderBrush property as follows

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit Width="255" Height="46" ErrorBorderBrush="DarkOrange"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.ErrorBorderBrush = Brushes.DarkOrange;

{% endhighlight %}

{% endtabs %}

![](Appearence_Images/Appearence_Img2.jpg)


## ShowPromptOnFocus


When the `ShowPromptOnFocus` is set to true, prompt characters are ignored when control loses focus. Again, the prompt characters are restored when the control is focused

### Example


{% tabs %}

{% highlight xaml %}

<syncfusion:SfMaskedEdit Width="255" Height="46" MaskType="Simple" Mask="(000) 000-0000" ShowPromptOnFocus="True"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType = MaskType.Simple;
maskedEdit.Mask = "(000) 000-0000";
maskedEdit.ShowPromptOnFocus = true;

{% endhighlight %}

{% endtabs %}

Control loses focus

![](Appearence_Images/Appearence_Img4.jpg)

Control gets focus

![](Appearence_Images/Appearence_Img3.jpg)