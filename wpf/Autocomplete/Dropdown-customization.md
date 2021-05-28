---
layout: post
title: Dropdown customization in WPF Autocomplete control | Syncfusion
description: Learn here all about Dropdown customization support in Syncfusion WPF Autocomplete (SfTextBoxExt) control and more.
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Dropdown customization in WPF Autocomplete (SfTextBoxExt)

Suggestion box is the drop-down list box, which displays the filtered suggestions inside a pop-up. This section explains the properties and customizations that deals with drop-down list in the `AutoComplete` control.

## Customize the background 

The [DropDownBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_DropDownBackground) property is used to modify the background color of suggestion box. The following code example demonstrates how to change the background color of suggestion box.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="300"
                      Height="40"
                      SearchItemPath="Name"
                      AutoCompleteMode="Suggest"
                      DropDownBackground="AliceBlue"
                      AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}
{% highlight c# %}

textBoxExt.DropDownBackground = new SolidColorBrush(Colors.AliceBlue);

{% endhighlight %}
{% endtabs %}

![Dropdown background color](Dropdown_customization_images/drop_down_background_color.png)


## Drop-down placement 

The [SuggestionBoxPlacement](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SuggestionBoxPlacement) property, defines the position of pop-up relative to the control. It contains three built-in options:

1. Top
2. Bottom
3. None

The default value is bottom.

### Top

The drop-down list will open at the top of the text field.

{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center"
                      VerticalAlignment="Center"
                      Width="300"
                      Height="40"
                      SearchItemPath="Name"
                      SuggestionBoxPlacement="Top"
                      AutoCompleteMode="Suggest"
                      SuggestionMode="StartsWith"
                      AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}
{% highlight c# %}

textBoxExt.SuggestionBoxPlacement = SuggestionBoxPlacement.Top;

{% endhighlight %}
{% endtabs %}

![Top](Dropdown_customization_images/Top.png)



### Bottom

The drop-down list will open at the bottom of the text field.

{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center"
                      VerticalAlignment="Center"
                      Width="300"
                      Height="40"
                      SearchItemPath="Name"
                      SuggestionBoxPlacement="Bottom"
                      AutoCompleteMode="Suggest"
                      SuggestionMode="StartsWith"
                      AutoCompleteSource="{Binding Employees}"/>
  
{% endhighlight %}
{% highlight c# %}

textBoxExt.SuggestionBoxPlacement = SuggestionBoxPlacement.Bottom;

{% endhighlight %}
{% endtabs %}

![Bottom](Dropdown_customization_images/Bottom.png)


### None

The drop-down list will show the filtered items.

{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center"
                      VerticalAlignment="Center"
                      Width="300"
                      Height="40"
                      SearchItemPath="Name"
                      SuggestionBoxPlacement="None"
                      AutoCompleteMode="Suggest"
                      SuggestionMode="StartsWith"
                      AutoCompleteSource="{Binding Employees}"/>
    
{% endhighlight %}
{% highlight c# %}

textBoxExt.SuggestionBoxPlacement = SuggestionBoxPlacement.None;

{% endhighlight %}
{% endtabs %}

![None](Dropdown_customization_images/None.png)


## Setting the maximum height 

The maximum height of the suggestion box in the AutoComplete control can be changed using the [MaximumDropDownHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_MaxDropDownHeight) property.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="400"
                      SearchItemPath="Name"
                      MaxDropDownHeight="500"
                      AutoCompleteMode="Suggest"
                      AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}
{% highlight c# %}

textBoxExt.MaxDropDownHeight = 500;

{% endhighlight %}
{% endtabs %}

![MaxDropDownHeight](Dropdown_customization_images/maximum_drop_down_height.png)

## Open the drop-down on focus 

Suggestion box can be shown whenever the control receives focus using the [ShowSuggestionsOnFocus](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_ShowSuggestionsOnFocus) property. At that time, suggestion list is the complete list of data source.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="400"
                      SearchItemPath="Name"
                      ShowSuggestionsOnFocus="True"
                      AutoCompleteMode="Suggest"
                      AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}
{% highlight c# %}

textBoxExt.ShowSuggestionsOnFocus = true;

{% endhighlight %}
{% endtabs %}

![ShowSuggestionsOnFocus](Dropdown_customization_images/suggestion_on_focus.png)

## Open drop-down with a delay 

The [PopupDelay](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_PopupDelay) specifies the delay after, which the suggestion pop-up should open. 

{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="400"
                      SearchItemPath="Name"
                      PopupDelay="00:00:02"
                      AutoCompleteMode="Suggest"
                      AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}
{% highlight c# %}

textBoxExt.PopupDelay = new TimeSpan(00,00,02);

{% endhighlight %}
{% endtabs %}



N> View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/Dropdown-customization) in GitHub
