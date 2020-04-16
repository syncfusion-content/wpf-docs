---
layout: post
title: Dealing with WPF ColorPickerPalette control | Syncfusion
description: Learn about selecting a different types of colors in Syncfusion WPF ColorPickerPalette control and more details about the control features.
platform: wpf
control: ColorPickerPalette
documentation: ug
---

# Dealing with WPF ColorPickerPalette

This section explains the different types of colors available in the [ColorPickerPalette](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette.html) and  how to choose the colors and its panel customizations.

## Accessing a Color programmatically

We can get or change the selected color of the `ColorPickerPalette` by setting the value to the [Color](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~Color.html) property. If we want know the selected color name, use the [ColorName](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~ColorName.html) property that holds the name of the selected color item. The default value of `Color` and `ColorName` property is `Black` and `Color`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette Color="Red"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.Color = Colors.Red;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette programmatically picked the red color](Dealing-with-ColorPickerPalette_images/Colorprogrammatically.png)

Here, `Red` color is selected color in the `ColorPickerPalette`.

## Setting automatic color

If we want to change the default selected color on application launching, set the value for [AutomaticColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~AutomaticColor.html) property. We can hide the automatic color visibility by setting the [AutomaticColorVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~AutomaticColorVisibility.html) property value as `Collapsed`. The default value of `AutomaticColor` property is `Black` and the default value of `AutomaticColorVisibility` property is `Visible`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette AutomaticColor="Green"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.AutomaticColor = Colors.Green;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with automatic color](Dealing-with-ColorPickerPalette_images/AutomaticColor.png)

## Select a predefined colors

We can select a color from either various theme color items or standard color items.

### Select a color from theme color items

We can select a various theme colors by setting the value for [Themes](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~Themes.html) property. Based on the `Themes` value, the respective base color items are displayed with its variants. If we want allow the user to select only base theme colors without its variants color, use the [GenerateThemeVariants](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~GenerateThemeVariants.html) property as `false`.  We can hide the theme color panel by setting the [ThemePanelVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~ThemePanelVisibility.html) property value as `Collapsed`.  The default value of `Themes` property is `Office` and default value of  `ThemePanelVisibility` property is `Visible`.

![ColorPickerPalette with various theme color items](Dealing-with-ColorPickerPalette_images/Themes.png)

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette Themes="Metro"
                               GenerateThemeVariants="True" 
                               ThemePanelVisibility="Visible"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.Themes = PaletteTheme.Metro;
colorPickerPalette.GenerateThemeVariants = true;
colorPickerPalette.ThemePanelVisibility = Visibility.Visible;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with metro theme color items](Dealing-with-ColorPickerPalette_images/ThemesPanel.png)

### Select a color from standard color items

We can select a standard colors from the standard color panel. If we want allow the user to select standard colors with its variant colors, use the [GenerateStandardVariants](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~GenerateStandardVariants.html) property as `true`.  We can hide the standard color panel by setting the [StandardPanelVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~StandardPanelVisibility.html) property value as `Collapsed`.  The default value of `GenerateStandardVariants` property is `false` and default value of  `StandardPanelVisibility` property is `Visible`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette GenerateStandardVariants="True" 
                               StandardPanelVisibility="Visible"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.GenerateStandardVariants = true;
colorPickerPalette.StandardPanelVisibility = Visibility.Visible;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with various standard color items](Dealing-with-ColorPickerPalette_images/StandardPanel.png)

## Show white and black color variants

If we want to allow the user to select the theme color from white or black or both color variants, use the [BlackWhiteVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~BlackWhiteVisibility.html) property as `White` or `Black` or `Both`. The default value of `BlackWhiteVisibility` property is `None`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette BlackWhiteVisibility="Both"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.BlackWhiteVisibility = BlackWhiteVisible.Both;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with black and white color variants](Dealing-with-ColorPickerPalette_images/BlackWhite.png)

## Add your own color in the palette

If we want to allow the user to select a color from own colors, add that color with its name using [CustomColor.ColorName](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.CustomColor~ColorName.html) and [CustomColor.Color](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.CustomColor~Color.html) into the [CustomColorsCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~CustomColorsCollection.html) and set the [SetCustomColors](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~SetCustomColors.html) property value as `true`. The provided `CustomColor.ColorName` is shown in the tooltip while mouse hovering on the color item. We can change the custom color panel header text and its visibility by using the [CustomHeaderText](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~CustomHeaderText.html) and [CustomHeaderVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~CustomHeaderVisibility.html) properties. The default value of `CustomHeaderText` is `CustomColors` and  default value of `CustomHeaderVisibility` is `Visible`.

{% tabs %}
{% highlight C# %}

public class ViewModel : NotificationObject {
    private ObservableCollection<CustomColor> newColorCollection;
    public ObservableCollection<CustomColor> NewColorCollection {
        get {
            return newColorCollection;
        }
        set {
            newColorCollection = value;
            this.RaisePropertyChanged("NewColorCollection");
        }
    }
    public ViewModel() {
        NewColorCollection = new ObservableCollection<CustomColor>();
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<Window.Resources>
    <local:ViewModel x:Key="viewModel">
        <local:ViewModel.NewColorCollection>

            <!-- Defining the color details -->
            <syncfusion:CustomColor Color="#FF11EBF8" ColorName="Aqua" />
            <syncfusion:CustomColor Color="#FFF80FA6" ColorName="Deep Pink" />
            <syncfusion:CustomColor Color="#FF8BA7C2" ColorName="Dark Gray" />
            <syncfusion:CustomColor Color="#F53CDF07" ColorName="Lime Green" />
            <syncfusion:CustomColor Color="#C2929545" ColorName="Olive Drab" />
            <syncfusion:CustomColor Color="#2E956145" ColorName="Sienna" />
            <syncfusion:CustomColor Color="#78458E95" ColorName="Steel Blue" />
            <syncfusion:CustomColor Color="#8B8220E4" ColorName="Blue Violet" />
        </local:ViewModel.NewColorCollection>
    </local:ViewModel>
</Window.Resources>

<syncfusion:ColorPickerPalette CustomColorsCollection="{Binding NewColorCollection}" 
                               CustomHeaderText="New Colors" 
                               CustomHeaderVisibility="Visible"
                               SetCustomColors="True"
                               DataContext="{StaticResource viewModel}"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with custom color items](Dealing-with-ColorPickerPalette_images/CustomColor.png)

Click [here]() to download the sample that showcases how to your own color items into the palette.

##  Recently used color items

The recently selected color items are displayed in the RecentlyUsedPanel. If we want to choose a color which are previously selected, use the RecentlyUsedPanel. We can hide the RecentlyUsedPanel by using the [RecentlyUsedPanelVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~RecentlyUsedPanelVisibility.html) property value as `Collapsed`. The default value of `RecentlyUsedPanelVisibility` property is `Visible`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette RecentlyUsedPanelVisibility="Visible"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.RecentlyUsedPanelVisibility = Visibility.Visible;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with recently used color items](Dealing-with-ColorPickerPalette_images/RecentPanel.png)

## Choosing a color from MoreColor window

In addition to colors in Theme colors and Standard colors, MoreColor feature allows you to select wide range of color options. MoreColor feature includes two categories namely Standard Colors and Custom Colors. We can hide the visibility of the MoreColor Option by using the [MoreColorOptionVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~MoreColorOptionVisibility.html) property value as `Collapsed`.

![ColorPickerPalette with more color panel](Dealing-with-ColorPickerPalette_images/MoreColorPanel.png)

### Selecting more standard colors

We can select color from 140 standard colors clustered in the shape of a Hexagon. If we want to hide the Standard color tab, use the [IsStandardTabVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~IsStandardTabVisible.html) property value as `Collapsed`. The color chosen from this cluster will also be added in the RecentlyUsedPanel.


{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette IsStandardTabVisible="Visible"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.IsStandardTabVisible = Visibility.Visible;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with standard color tab](Dealing-with-ColorPickerPalette_images/StandardColorPanel.png)

### Selecting more custom colors

We can select any color with own saturation level by using the custom tab color picker . If we want to hide the custom color tab, use the [IsCustomTabVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~IsCustomTabVisible.html) property value as `Collapsed`. The color chosen from this color picker will also be added in the RecentlyUsedPanel.


{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette IsCustomTabVisible="Visible"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.IsCustomTabVisible = Visibility.Visible;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with custom color tab](Dealing-with-ColorPickerPalette_images/CustomColorPanel.png)

N> If we set `IsCustomTabVisible` and `IsStandardTabVisible` property value as `false`, then MoreColor panel automatically hides.

## Color changed notification

The selected color changed in `ColorPickerPalette` can be examined using [ColorChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~ColorChanged_EV.html) event. The `ColorChanged` event contains the old and newly selected color values.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette ColorChanged="ColorPickerPalette_ColorChanged"
                               Name="ColorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.ColorChanged += ColorPickerPalette_ColorChanged;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

//Invoked when the selected color is changed
private void ColorPickerPalette_ColorChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {
    Console.WriteLine(e.OldValue.ToString());
    Console.WriteLine(e.NewValue.ToString());
}

{% endhighlight %}
{% endtabs %} 

## Tooltip support

Tooltip is used to show the information about the segment, when you mouse over on the segment. We can show information about the name of the color item using tooltip when hovering the mouse on the specific color item.

![ColorPickerPalette with tooltip support](Appearance_images/tooltip.gif)

## Expanded mode

If we want to directly use the `ColorPickerPalette` without drop down, set the [IsExpanded](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~IsExpanded.html) property value as `true`. The default value of `IsExpanded` is `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette IsExpanded="true"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.IsExpanded = true;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette with expanded mode](Dealing-with-ColorPickerPalette_images/Expanded.png)

## Change color item size

We can change each color item size by using the [BorderWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~BorderWidth.html) and [BorderHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~BorderHeight.html) properties.  Based on the color items size, the color palette is resized. The default value of `BorderWidth` and `BorderHeight` properties is `17`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette BorderWidth="30" 
                               BorderHeight="30"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.BorderWidth = 30;
colorPickerPalette.BorderHeight = 30;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette color item size changed](Dealing-with-ColorPickerPalette_images/ColorSize.png)


## Change color palette size

We can change the color palette pop size by using the [PopupWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~PopupWidth.html) and [PopupHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~PopupHeight.html) properties. Based on the popup color palette size, the color items are resized. The default value of `PopupWidth` and `PopupHeight` properties is `175` and `200`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette PopupWidth="120" 
                               PopupHeight="100"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% highlight C# %}

ColorPickerPalette colorPickerPalette = new ColorPickerPalette();
colorPickerPalette.PopupWidth = 120;
colorPickerPalette.PopupHeight = 100;
colorPickerPalette.Width = 60;
colorPickerPalette.Height = 40;

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette popup size changed](Dealing-with-ColorPickerPalette_images/PopUpSize.png)


N> If we set both `PopupWidth` & `PopupHeight` and `BorderWidth` & `BorderHeight`, then `BorderWidth` & `BorderHeight` properties have higher priority.

## Change header and more color icons

We can set the icons for control header which is placed left to the DropDown button and more color panel header by using the [Icon](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~Icon.html) and [MoreColorsIcon](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~MoreColorsIcon.html) properties. We can change the icon size for the control icon and more color icon by using the [IconSize](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~IconSize.html) and [MoreColorsIconSize](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.ColorPickerPalette~MoreColorsIconSize.html) properties.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPickerPalette Icon="/Label.png"
                               IconSize="18,18"
                               MoreColorsIcon="/MoreColor.png"
                               MoreColorsIconSize="50,50"
                               Name="colorPickerPalette" 
                               Width="60"
                               Height="40">
</syncfusion:ColorPickerPalette>

{% endhighlight %}
{% endtabs %}

![ColorPickerPalette popup size changed](Dealing-with-ColorPickerPalette_images/Icons.png)

Click [here]() to download the sample that showcases features and  different type color items with its panel visibility customization.
