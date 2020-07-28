---
layout: post
title: Working with with WPF SfRadialSlider control | Syncfusion
description: Learn here about working of Syncfusion WPF SfRadialSlider control and more details about the control features.
platform: WPF
control: SfRadialSlider
documentation: ug
---

# Working with WPF SfRadialSlider

This section explains different UI customization and common features available in [SfRadialSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider.html) control.

## Select tick value

You can select any tick value by dragging the pointer along the circular track or clicking on the corresponding track value. You can get the selected value by using the `Value` property. The default value of `Value` property is `0`.

![Selecting a value by click and draging](GettingStarted_images/SelectValue.gif)

### Select tick value programmatically

You can select a tick value programmatically by assigning the tick value to the `Value` property.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfRadialSlider Value="34"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.Value = 34;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider selecting a value programmatically](GettingStarted_images/SelectedValue.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Display selected value

You can display the selected value in the content area of the `SfRadialSlider` by setting the selected value to the [Content](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~Content.html) property. The default value of `Content` property is `null`.

{% tabs %}
{% highlight C# %}

public class ViewModel
{
    private double selectedValue;

    public double SelectedValue {
        get {
            return selectedValue;
        }
        set {
            selectedValue= value;
        }
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

<syncfusion:SfRadialSlider Content="{Binding SelectedValue,Mode=TwoWay}"
                           Value="{Binding SelectedValue,Mode=TwoWay}" 
                           Name="radialSlider">
    <syncfusion:SfRadialSlider.DataContext>
        <local:ViewModel/>
    </syncfusion:SfRadialSlider.DataContext>
</syncfusion:SfRadialSlider>

{% endhighlight %}
{% endtabs %}

![SfRadialSlider displays the selected value](GettingStarted_images/DisplaySelectedValue.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Custom UI for display content

You can customize the appearance of display content area by using the `ContentTemplate` property. The default value of `ContentTemplate` property is `null`. The `DataContext` of the `ContentTemplate` property is `SfRadialSlider`.

{% tabs %}
{% highlight C# %}

public class ViewModel
{
    private double selectedValue;

    public double SelectedValue {
        get {
            return selectedValue;
        }
        set {
            selectedValue= value;
        }
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Value="{Binding SelectedValue,Mode=TwoWay}" 
                           Name="radialSlider">
    <syncfusion:SfRadialSlider.ContentTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding SelectedValue}"
                       FontWeight="Bold" 
                       Background="Yellow"/>
        </DataTemplate>
    </syncfusion:SfRadialSlider.ContentTemplate>

    <syncfusion:SfRadialSlider.DataContext>
        <local:ViewModel/>
    </syncfusion:SfRadialSlider.DataContext>
</syncfusion:SfRadialSlider>

{% endhighlight %}
{% endtabs %}

![SfRadialSlider with customized content area](Working-With-SfRadialSlider_images/ContentTemplate.png)

## Change min-max tick value

You can change the minimum and maximum ticks value of the `SfRadialSlider` by using the `Minimum` and `Maximum` properties. The default value of `Minimum` property is `0` and `Maximum` property is `100`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Minimum="100"
                           Maximum="200"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.Minimum = 100;
radialSlider.Maximum = 200;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider with changed minimum and maximum values](GettingStarted_images/min-max.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Change start and end position

You can change starting and ending position for generating the ticks in the circular track by using the [StartAngle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~StartAngle.html) and [EndAngle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~EndAngle.html) properties. The default value of `StartAngle` property is `0` and `StartAngle` property is `360`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider StartAngle="90"
                           EndAngle="330"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.StartAngle = 90;
radialSlider.EndAngle = 300;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider ticks start and end position changed](GettingStarted_images/Start-EndAngle.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Change tick display interval

You can change the tick display interval from the `Minimum` to `Maximum` values by using the [TickFrequency](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~TickFrequency.html) property. Based on `TickFrequency`'s multiples, the display interval is set from `Minimum` to `Maximum` value.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider TickFrequency="20"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.TickFrequency = 20;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider ticks display interval changed to 20](GettingStarted_images/TickFrequency.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Step interval

If you want to control the smallest possible range of value to be selected in `SfRadialSlider`, use the `SmallChange` property. The default value of `SmallChange` property is `0.1`. For example, if `SmallChange` is set to `5`, then it is only possible to select values that are multiples of `5`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider SmallChange="5"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.SmallChange = 5;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider value selection interval changed](GettingStarted_images/SmallChange.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Change tick direction

You can change the ticks direction either clockwise or counter-clockwise direction by using the [SweepDirection](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~SweepDirection.html) property. The default value of `SweepDirection` property is `Clockwise`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider SweepDirection="Counterclockwise" 
                           StartAngle="180" 
                           EndAngle="360" 
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.SweepDirection = SweepDirection.Counterclockwise;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider ticks displayed in counter-clockwise](GettingStarted_images/SweepDirection.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Show maximum value

By default, the maximum value is not shown in the `SfRadialSlider`. If you want to show the maximum value when difference of the minimum and maximum value is not a `TickFrequency` multiples, use the [ShowMaximumValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~ShowMaximumValue.html) property value as `true`. The default value of `ShowMaximumValue` property is `false`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider TickFrequency="9" 
                           ShowMaximumValue="True"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.TickFrequency = 9;
radialSlider.ShowMaximumValue = true;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider shows the maximum value](Working-With-SfRadialSlider_images/ShowMaximumValue.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Change tick radius

You can change the each tick radius by using the [TickRadiusFactor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~TickRadiusFactor.html) property. The default value of `TickRadiusFactor` property is `0.72`. You can hide the ticks by using the [TickVisibility](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~TickVisibility.html) property value as `Hidden`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider TickRadiusFactor="0.5"
                           TickVisibility="Visible" 
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.TickRadiusFactor = 0.5;
radialSlider.TickVisibility = Visibility.Visible;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider ticks radius factor changed to 0.5](Working-With-SfRadialSlider_images/TickRadiusFactor.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

### Custom UI of ticks

You can customize the appearance of ticks by using the `TickTemplate` property. The default value of `TickTemplate` property is `null`. The `DataContext` of the `TickTemplate` property is `SfRadialSlider` tick value count.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Name="radialSlider">
    <syncfusion:SfRadialSlider.TickTemplate>
        <DataTemplate>
            <Border Background="Red"/>
        </DataTemplate>
    </syncfusion:SfRadialSlider.TickTemplate>
</syncfusion:SfRadialSlider>

{% endhighlight %}
{% endtabs %}

![SfRadialSlider with customized ticks](Working-With-SfRadialSlider_images/TickTemplate.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/Custom-UI)

## Change tick label radius

You can change the each tick label radius by using the [LabelRadiusFactor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~LabelRadiusFactor.html) property. The default value of `LabelRadiusFactor` property is `0.87`. You can hide the tick labels by using the [LabelVisibility](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~LabelVisibility.html) property value as `Hidden`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider LabelRadiusFactor="0.5"
                           LabelVisibility="Visible" 
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.LabelRadiusFactor = 0.5;
radialSlider.LabelVisibility = Visibility.Visible;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider tick label radius factor changed to 0.5](Working-With-SfRadialSlider_images/LabelRadiusFactor.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

### Custom UI of tick labels

You can customize the appearance of tick labels by using the `LabelTemplate` property. The default value of `LabelTemplate` property is `null`. The `DataContext` of the `LabelTemplate` property is `SfRadialSlider` tick values.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Name="radialSlider">
    <syncfusion:SfRadialSlider.LabelTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding}"
                       Foreground="Red"
                       Background="Yellow"/>
        </DataTemplate>
    </syncfusion:SfRadialSlider.LabelTemplate>
</syncfusion:SfRadialSlider>

{% endhighlight %}
{% endtabs %}

![SfRadialSlider with customized tick labels](Working-With-SfRadialSlider_images/LabelTemplate.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/Custom-UI)

## Change inner rim radius

You can change inner rim(circle in the center of radial slider) radius of the `SfRadialSlider` by using the [InnerRimRadiusFactor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~InnerRimRadiusFactor.html) property. The default value of `InnerRimRadiusFactor` property is `0.2`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider InnerRimRadiusFactor="0.5" 
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.InnerRimRadiusFactor = 0.5;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider inner rim radius changed](Working-With-SfRadialSlider_images/InnerRadius.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

### Custom appearance of inner rim

You can change the background of the inner rim by using the [InnerRimFill](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~InnerRimFill.html) 
property. You can also change the border color and border thickness of the inner rim by using the [InnerRimStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~InnerRimStroke.html) and [InnerRimStrokeThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~InnerRimStrokeThickness.html) properties. The default value of `InnerRimStroke` property is `Light SlateGray` and `InnerRimStrokeThickness` property is `2`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider InnerRimFill="Yellow" 
                           InnerRimStroke="Red" 
                           InnerRimStrokeThickness="4"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.InnerRimFill = Brushes.Yellow;
radialSlider.InnerRimStroke = Brushes.Red;
radialSlider.InnerRimStrokeThickness = 4;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider inner rim appearance changed](Working-With-SfRadialSlider_images/InnerUI.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Change outer rim radius

You can change outer rim radius of the `SfRadialSlider` by using the [OuterRimRadiusFactor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~OuterRimRadiusFactor.html) properties. The default value of `OuterRimRadiusFactor` property is `0.7`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider OuterRimRadiusFactor="0.5"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.OuterRimRadiusFactor = 0.5;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider outer rim radius changed](Working-With-SfRadialSlider_images/OuterRadius.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

### Custom appearance of outer rim

You can change the fill color of the outer rim by using the `Background` property. You can also change the border color and border thickness of the outer rim by using the [OuterRimStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~OuterRimStroke.html) and [OuterRimStrokeThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~InnerRimStrokeThickness.html) properties. The default value of `OuterRimStroke` property is `Rosy Brown` and `OuterRimStrokeThickness` property is `2`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Background="Yellow" 
                           OuterRimStroke="Red" 
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.Background = Brushes.Yellow;
radialSlider.OuterRimStroke = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider outer rim appearance changed](Working-With-SfRadialSlider_images/OuterUI.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

## Change selection pointer radius

You can change the selection pointer radius by using the [PointerRadiusFactor](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~PointerRadiusFactor.html) property. The default value of `PointerRadiusFactor` property is `0.75`. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider PointerRadiusFactor="0.5"
                           Name="radialSlider" />

{% endhighlight %}
{% highlight C# %}

radialSlider.PointerRadiusFactor = 0.5;

{% endhighlight %}
{% endtabs %}

![SfRadialSlider selection pointer radius factor changed to 0.5](Working-With-SfRadialSlider_images/PointerRadiusFactor.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/RadialSlider-Features)

### Custom UI of selection pointer

You can customize the appearance of selection pointer by using the [PointerStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~PointerStyle.html) property. The `DataContext` of the `PointerStyle` property is `syncfusion:RadialPointer`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Name="radialSlider">
    <syncfusion:SfRadialSlider.PointerStyle>
        <Style TargetType="syncfusion:RadialPointer">
            <Setter Property="Height" Value="2"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="syncfusion:RadialPointer">
                        <Border  Background="Red"/>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:SfRadialSlider.PointerStyle>
</syncfusion:SfRadialSlider>

{% endhighlight %}
{% endtabs %}

![SfRadialSlider with customized selection pointer](Working-With-SfRadialSlider_images/PointerStyle.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/Custom-UI)

### Custom UI of preview selection pointer

You can customize the appearance of preview selection pointer by using the [PreviewPointerStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~PreviewPointerStyle.html) property. The `DataContext` of the `PreviewPointerStyle` property is `syncfusion:RadialPreviewPointer`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider Name="radialSlider">
    <syncfusion:SfRadialSlider.PreviewPointerStyle>
        <Style TargetType="syncfusion:RadialPreviewPointer">
            <Setter Property="Height" Value="2"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="syncfusion:RadialPreviewPointer">
                        <Border Opacity="0.2"  Background="Red"/>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:SfRadialSlider.PreviewPointerStyle>
</syncfusion:SfRadialSlider>

{% endhighlight %}
{% endtabs %}

![SfRadialSlider with customized preview selection pointer](Working-With-SfRadialSlider_images/PreviewPointerStyle.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/Custom-UI)

## Text formatting

You can customize the text format for the specific or all tick labels by handling the [DrawLabel](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~DrawLabel_EV.html) event and setting the [DrawLabelEventArgs.Handled](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.DrawLabelEventArgs~Handled.html) property value as `true`. You can change the content and foreground of the tick labels by using the [DrawLabelEventArgs.Text](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.DrawLabelEventArgs~Text.html) and [DrawLabelEventArgs.Foreground](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.DrawLabelEventArgs~Foreground.html) properties. You can also change the font family and font size of the tick labels by using the [DrawLabelEventArgs.FontFamily](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.DrawLabelEventArgs~FontFamily.html) and [DrawLabelEventArgs.FontSize](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.DrawLabelEventArgs~FontSize.html) properties.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadialSlider DrawLabel="sfRadialSlider_DrawLabel"  
                           Name="sfRadialSlider">           
    <TextBlock Text="{Binding ElementName=sfRadialSlider, Path=Value}" 
               FontSize="15"
               HorizontalAlignment="Center"
               VerticalAlignment="Center"/>
</syncfusion:SfRadialSlider>

{% endhighlight %}
{% highlight C# %}

sfRadialSlider.DrawLabel += sfRadialSlider_DrawLabel;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows,

{% tabs %}
{% highlight c# %}

private void sfRadialSlider_DrawLabel(object sender, DrawLabelEventArgs e) {            
    e.Handled = true;
    e.Text += "°C";
    if (e.Value <= 33) {
        e.FontSize = 8;
        e.FontFamily = new FontFamily("Arial");
        e.Foreground = Brushes.Green;
    }
    else if (e.Value > 33 && e.Value <= 66) {
        e.FontSize = 10;
        e.FontFamily = new FontFamily("Courier");
        e.Foreground = Brushes.Gold;
    }
    else {
        e.FontSize = 12;
        e.FontFamily = new FontFamily("Georgia");
        e.Foreground = Brushes.Red;
    }
}

{% endhighlight %}
{% endtabs %}

![Change tick label text formatting](Ticks_images/LabelEdit.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-radial-slider-examples/tree/master/Samples/Label-Formatting)

 ## Value changed notification

The selected value changed in `SfRadialSlider` can be examined using `ValueChanged` event. The `ValueChanged` event contains the old and newly selected tick value in the `OldValue` and `NewValue` properties.

{% tabs %}
{% highlight XAML %}

 <syncfusion:SfRadialSlider ValueChanged="RadialSlider_ValueChanged" 
                      Name="radialSlider"/>

{% endhighlight %}
{% highlight C# %}

SfRadialSlider radialSlider = new SfRadialSlider();
radialSlider.ValueChanged += RadialSlider_ValueChanged;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows,

{% tabs %}
{% highlight C# %}

private void RadialSlider_ValueChanged(object sender, RoutedPropertyChangedEventArgs<double> e){
    //Get old and new selected tick value
    var oldValue = e.OldValue;
    var newValue = e.NewValue;
}

{% endhighlight %}
{% endtabs %}
