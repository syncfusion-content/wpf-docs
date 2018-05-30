---
layout: post
title: Validation| SfMaskedEdit | Wpf | Syncfusion
description: validation
platform: wpf
control: SfMaskedEdit
documentation: ug
---

# ValidationMode

Input validation happens based on the value of the `ValidationMode` property. The enum values of this property are 

  * LostFocus
  * KeyPress
  * HasError

## KeyPress

When the `ValidationMode` is KeyPress, the validation is raised for each key press.

## LostFocus

When the `ValidationMode` is LostFocus, the validation takes place when the control lost its focus

## HasError

This read only property is used to check whether the validation succeeds or not. It returns true once validation succeeds or else set to false. The following code example shows the usage of HasError property.

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

## Custom Validation

In `SfMaskedEdit` control there is no event for the validation. The custom validation based on the `ValidationMode` property of `SfMaskedEdit` using attached properties of Validation class. Also `HasError` property has been used for Validation in source level.

Custom validation can be implemented as follows

Step 1. Create a class inherited from `ValidationRule`.

Step 2. Override ValidationResult property and implement custom validation logic.

For Example:
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

{% tabs %}
{% highlight xaml %}
Step3. Set Triggers for KeyPress and LostFocus ValidationMode

		<Trigger Property="ValidationMode" Value="KeyPress">
            <Setter Property="Text">
                <Setter.Value>
                    Binding Path="Value" Mode="TwoWay" UpdateSourceTrigger="PropertyChanged">
                        <Binding.ValidationRules>
                             <local:NameValidator/>
                        </Binding.ValidationRules>
                    </Binding>
                </Setter.Value>
            </Setter>
        </Trigger>
        	
{% endhighlight %}
{% endtabs %}