---
layout: post
title: Appearance of WPF AutoComplete | Syncfusion
description: Learn here about how to set the different style of theme to the Syncfusion WPF AutoComplete control.
platform: wpf
control: AutoComplete
documentation: ug
---

# Appearance of WPF AutoComplete

## Theme

AutoComplete supports various built-in themes. Refer to the below links to apply themes for the AutoComplete,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

   ![Setting theme to WPF AutoComplete](Getting-Started_images/Getting-Started_img15.png)


## Show the shadow effect

You can show the shadow effect of AutoComplete by using [DropShadowEffect](https://docs.microsoft.com/en-us/dotnet/api/system.windows.media.effects.dropshadoweffect?view=netcore-3.1). You can also set the distance between the control and shadow by using [ShadowDepth](https://docs.microsoft.com/en-us/dotnet/api/system.windows.media.effects.dropshadoweffect.shadowdepthproperty?view=netcore-3.1) property.

Refer the below code for your reference.

{% tabs %}

{% highlight XAML %}

<syncfusion:AutoComplete Height="30" Width="150" Text="AutoComplete">
    <syncfusion:AutoComplete.Effect>
        <DropShadowEffect ShadowDepth="10" Color="LightGray" Opacity="2" />
    </syncfusion:AutoComplete.Effect>
</syncfusion:AutoComplete>

{% endhighlight %}

{% highlight C# %}

AutoComplete autoComplete = new AutoComplete();
autoComplete.Height = 30;
autoComplete.Width = 150;
autoComplete.Text = "AutoComplete";
DropShadowEffect shadowEffect = new DropShadowEffect();
shadowEffect.ShadowDepth = 10;
shadowEffect.Color = Colors.LightGray;
shadowEffect.Opacity = 2;
autoComplete.Effect = shadowEffect;
grid.Children.Add(autoComplete);

{% endhighlight %}

{% endtabs %}

![Show the shadow effects of WPF AutoComplete](Appearance_images/wpf-autocomplete-shadow.png)
