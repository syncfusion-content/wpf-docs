---
layout: post
title: Hint Position in WPF TextInputLayout | Syncfusion®
description: Hint Position in SfTextInputLayout enables controlling how hint labels float, remain visible, or hide based on input focus.
platform: wpf
control: SfTextInputLayout
documentation: ug
---

# Hint Position in WPF TextInputLayout (SfTextInputLayout)

The display behavior of the floating label can be controlled by setting the `HintFloatMode` property.

N> The default value of `HintFloatMode` is `Float`.

## Float

The hint label floats to the top of the input view when the input view is focused.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout 
    Hint="Name"
    HintFloatMode="Float" 
    HelperText="Enter your name">
    <TextBox />
</inputLayout:SfTextInputLayout>
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.HintFloatMode = HintFloatMode.Float;
inputLayout.HelperText= "Enter your name";
inputLayout.InputView = new TextBox(); 

{% endhighlight %}

{% endtabs %}

![WPF TextInputLayout Float](Images/Float.png)


## AlwaysFloat

The hint label is always positioned at the top of the input view.

{% tabs %} 

{% highlight xaml %} 

 <inputLayout:SfTextInputLayout 
    Hint="Name"
    HintFloatMode="AlwaysFloat" 
    HelperText="Enter your name">
    <TextBox />
</inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.HintFloatMode = HintFloatMode.AlwaysFloat;
inputLayout.HelperText= "Enter your name";
inputLayout.InputView = new TextBox(); 

{% endhighlight %}

{% endtabs %}

![WPF TextInputLayout AlwaysFloat](Images/AlwaysFloat.png)


## None

The hint label is hidden when the input view is focused.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout 
    Hint="Name"
    HintFloatMode= "None"
    HelperText="Enter your name">
    <TextBox />
</inputLayout:SfTextInputLayout> 
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.HintFloatMode = HintFloatMode.None;
inputLayout.HelperText= "Enter your name";
inputLayout.InputView = new TextBox(); 

{% endhighlight %}

{% endtabs %}

![WPF TextInputLayout None type](Images/HintLabelHidden.png)



