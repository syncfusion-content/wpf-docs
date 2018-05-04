---
layout: post
title: ValidationMode| SfMaskedEdit | Wpf | Syncfusion
description: validationmode
platform: wpf
control: SfMaskedEdit
documentation: ug
---

# ValidationMode

Input validation happens based on the value of the ValidationMode property. The enum values of this property are 

  * LostFocus
  * KeyPress

When the ValidationMode is KeyPress, the validation is raised for each key press. For LostFocus, the validation take place when the control get lost its focus. 

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
