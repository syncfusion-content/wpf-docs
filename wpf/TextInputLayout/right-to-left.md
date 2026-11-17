---
layout: post
title: Right-to-Left in WPF TextInputLayout | Syncfusion®
description: Right-to-Left Support in SfTextInputLayout enables displaying text and input layouts correctly for RTL languages.
platform: wpf
control: SfTextInputLayout
documentation: ug
---

# Right to Left in WPF TextInputLayout (SfTextInputLayout)

`SfTextInputLayout` supports changing the text flow to the right-to-left direction by setting the `FlowDirection` property to `RightToLeft`.

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

