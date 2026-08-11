---
layout: post
title: Right to Left in WPF TextInputLayout | Syncfusion
description: Display the Syncfusion WPF TextInputLayout (SfTextInputLayout) control in right-to-left layouts for languages such as Arabic and Hebrew.
platform: wpf
control: SfTextInputLayout
documentation: ug
---

# Right to Left in WPF TextInputLayout

The TextInputLayout supports to change the flow of text to the right-to-left direction by setting the `FlowDirection` to `RightToLeft`.

{% tabs %}
{% highlight xaml %}

    <inputLayout:SfTextInputLayout
            x:Name="textinputlayout" 
            FlowDirection="RightToLeft"
            ContainerType="Outlined"
            Hint="نام"  
            HelperText="اپنا نام درج کریں" >
            <TextBox Text="جانسن" />
    </inputLayout:SfTextInputLayout>

{% endhighlight %}
{% highlight c# %}

textinputlayout.FlowDirection = FlowDirection.RightToLeft;
textinputlayout.ContainerType = ContainerType.Outlined;
textinputlayout.Hint = "نام";
textinputlayout.HelperText = "اپنا نام درج کریں";
textinputlayout.InputView = new TextBox() { Text = "جانسن"}; 

{% endhighlight %}
{% endtabs %}

![TextInputLayout with right to left](Images/RTL.png)

