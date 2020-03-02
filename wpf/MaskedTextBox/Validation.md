---
layout: post
title: Validation| SfMaskedEdit | Wpf | Syncfusion
description: Learn here about this section explains about validation mode of the Syncfusion WPF SfMaskedEdit control.
platform: wpf
control: SfMaskedEdit
documentation: ug
---

# ValidationMode of SfMaskedEdit

Input validation is based on the value of [ValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfMaskedEdit~ValidationMode.html) property. Enum values of this property are: 

* LostFocus
* KeyPress
* HasError

## KeyPress

When the [ValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfMaskedEdit~ValidationMode.html) is KeyPress, the validation is raised for each key press.

## LostFocus

When the [ValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfMaskedEdit~ValidationMode.html) is LostFocus, the validation takes place when the control lost its focus.

## HasError

This read only property is used to check whether the validation succeeds or not. It returns true once validation succeeds, or else set to be false. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfMaskedEdit x:Name="sfMaskedEdit" MaskType="Simple" Mask="00/00/0000" Value="14/11/2014" ValidationMode="LostFocus" LostFocus="sfMaskedEdit_LostFocus"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

private void sfMaskedEdit_LostFocus(object sender, RoutedEventArgs e)
{
    if (sfMaskedEdit.HasError)
    {
        MessageBox.Show("Please enter the correct date");
    }
}

{% endhighlight %}
{% endtabs %}

## Custom validation

In the `SfMaskedEdit` control, there is no event for the validation. The custom validation is based on the [ValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfMaskedEdit~ValidationMode.html) property by using the attached properties of Validation class. The [HasError](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfMaskedEdit~HasError.html) property is also used for source level validation.

Custom validation can be implemented by as follows:

1) Create a class inherited from `ValidationRule`.

2) Override the ValidationResult property and implement custom validation logic.

{% tabs %}

{% highlight C# %}

public class NameValidator : ValidationRule
{
    public override ValidationResult Validate
	(object value, System.Globalization.CultureInfo cultureInfo)
        {
        	if (value == null)
                return new ValidationResult(false, "value cannot be empty.");
            else
            	{
                    if (value.ToString() == "__/__/____" || value.ToString().Contains("_")) 
                    	return new ValidationResult(false, "Name cannot be more than 8 characters long.");
            	}
            return ValidationResult.ValidResult;
        }
}

{% endhighlight %}

{% endtabs %}

3) Set Triggers for KeyPress and LostFocus validation modes.

{% tabs %}

{% highlight XAML %}

<Trigger Property="ValidationMode" Value="KeyPress">
    <Setter Property="Text">
        <Setter.Value>
            <Binding Path="Value" Mode="TwoWay" UpdateSourceTrigger="PropertyChanged">
                <Binding.ValidationRules>
                    <local:NameValidator/>
                </Binding.ValidationRules>
            </Binding>
        </Setter.Value>
    </Setter>
</Trigger>
        	
{% endhighlight %}

{% endtabs %}