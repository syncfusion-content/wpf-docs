---
layout: post
title: Appearance of the WPF SfMaskedEdit control | Syncfusion
description: Learn about UI customization, theme support in Syncfusion WPF SfMaskedEdit control and more details about the control features.
platform: wpf
control: SfMaskedEdit
documentation: ug
---

# Appearance in WPF SfMaskedEdit

This section explains different UI customization and theming options available in [SfMaskedEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfMaskedEdit.html).

## Setting the background

You can change the default background color and selection color of `SfMaskedEdit` by using the `Background` and `SelectionBrush` property. The default value of `Background` property is `White` and `SelectionBrush` property is `Royal Blue`.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfMaskedEdit Background="Yellow"
                         SelectionBrush="Green"
                         Name="sfMaskedEdit"/>

{% endhighlight %}
{% highlight C# %}

SfMaskedEdit sfMaskedEdit = new SfMaskedEdit();
sfMaskedEdit.Background = Brushes.Yellow;
sfMaskedEdit.SelectionBrush = Brushes.Green;

{% endhighlight %}
{% endtabs %}

![SfMaskedEdit with yellow background](Appearence_Images/Background.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-maskedtextbox-examples/tree/master/Samples/Appearance) in GitHub

## Setting the foreground

You can change the foreground color by using the `Foreground` property and can change the caret color by using the `CaretBrush` property. The default value of `Foreground` property is `Black` and `CaretBrush` property is `null`.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfMaskedEdit Foreground="Blue" 
                         CaretBrush="Red"
                         Name="sfMaskedEdit"/>

{% endhighlight %}
{% highlight C# %}

SfMaskedEdit sfMaskedEdit = new SfMaskedEdit();
sfMaskedEdit.Foreground = Brushes.Blue;
sfMaskedEdit.CaretBrush = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![SfMaskedEdit with red foreground](Appearence_Images/Foreground.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-maskedtextbox-examples/tree/master/Samples/Appearance) in GitHub

## Setting the border color

You can change the default border color of `SfMaskedEdit` by using the `BorderBrush` property. The default value of `BorderBrush` property is `Lavender`.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfMaskedEdit BorderBrush="Blue"
                         Name="sfMaskedEdit"/>

{% endhighlight %}
{% highlight C# %}

SfMaskedEdit sfMaskedEdit = new SfMaskedEdit();
sfMaskedEdit.BorderBrush = Brushes.Blue;

{% endhighlight %}
{% endtabs %}

![SfMaskedEdit with yellow background](Appearence_Images/BorderColor.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-maskedtextbox-examples/tree/master/Samples/Appearance) in GitHub

## Change flow direction

You can change the flow direction of the `SfMaskedEdit` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfMaskedEdit FlowDirection="RightToLeft"
                         Name="sfMaskedEdit"/>

{% endhighlight %}
{% highlight C# %}

SfMaskedEdit sfMaskedEdit = new SfMaskedEdit();
sfMaskedEdit.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![SfMaskedEdit with RightToLeft flow direction](Appearence_Images/FlowDirection.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-maskedtextbox-examples/tree/master/Samples/Appearance) in GitHub

## Theme

You can customize the appearance of the `SfMaskedEdit` control by using the [SfSkinManager.SetVisualStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinmanager.SfSkinmanager.html#Syncfusion_SfSkinManager_SfSkinManager_SetVisualStyle_System_Windows_DependencyObject_Syncfusion_SfSkinManager_VisualStyles_) method and `SfSkinManager.VisualStyle` property . The following are the various built-in visual styles for `SfMaskedEdit` control.

* Blend
* Default
* Lime
* MaterialDark
* MaterialDarkBlue
* MaterialLight
* MaterialLightBlue
* Metro
* Office2010Black
* Office2010Blue
* Office2010Silver
* Office2013DarkGray
* Office2013LightGray
* Office2013White
* Office2016Colorful
* Office2016DarkGray
* Office2016White
* Office365
* Saffron
* SystemTheme
* VisualStudio2013
* VisualStudio2015

Here, the `Blend` style is applied to the `SfMaskedEdit`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfMaskedEdit syncfusionskin:SfSkinManager.VisualStyle="Blend" 
                         Name="sfMaskedEdit"/>

{% endhighlight %}
{% highlight C# %}

//Namespace for the SfSkinManager.
using Syncfusion.SfSkinManager;

SfMaskedEdit sfMaskedEdit = new SfMaskedEdit();
SfSkinManager.SetVisualStyle(sfMaskedEdit, VisualStyles.Blend);

{% endhighlight %}
{% endtabs %}

![SfMaskedEdit with Blend visual style](Appearence_Images/Theme.png)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-maskedtextbox-examples/tree/master/Samples/Themes) in GitHub