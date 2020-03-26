---
layout: post
title: Done and Cancel Buttons | SfDatePicker | WPF | Syncfusion
description: Deals with the Visibility of Done and Cancel Buttons of SfDatePicker contol for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Footer

## Ok and Cancel buttons

The selected date from the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) can be updated in the [SfDatePicker.Value](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~Value.html) property on after clicking `OK` buttons. 

## Show or hide the ok and cancel button

If we want to hide the `Ok` and `Cancel` buttons, you can use the 
[SfDateSelector.ShowDoneButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~ShowDoneButton.html) and [SfDateSelector.ShowCancelButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~ShowCancelButton.html) properties values as `false`. The default value of `SfDateSelector.ShowDoneButton` and `SfDateSelector.ShowCancelButton` properties values is `true`.

{% highlight XAML %}

<syncfusion:SfDatePicker Name="sfdatePicker" 
                         IsDropDownOpen="True"
                         Width="200">
    <syncfusion:SfDatePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfDateSelector">
            <!--Ok button hided-->
            <Setter Property="ShowDoneButton" Value="False"/>
            <!--Cancel button hided-->
            <Setter Property="ShowCancelButton" Value="False"/>
        </Style>
    </syncfusion:SfDatePicker.SelectorStyle>
</syncfusion:SfDatePicker>
		
{% endhighlight %}

![SfdatePicker hides the cancel and done button](Features_images/Features_img11.png)

Click [here]() to download the sample that showcases the `OK` and `Cancel` button visibility.
