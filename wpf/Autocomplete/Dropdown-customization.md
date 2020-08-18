---
layout: post
title: Suggestion box AutoComplete | SfTextBoxExt | wpf | Syncfusion
description: This section provides the details of the suggestion box and their placement in AutoComplete in `SfTextBoxExt`.
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Drop-down customization 

Suggestion box is the drop-down list box, which displays the filtered suggestions inside a pop-up. This section explains the properties and customizations that deals with drop-down list in the `AutoComplete` control.

## Customize the background 

The [DropDownBackground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~DropDownBackground.html) property is used to modify the background color of suggestion box. The following code example demonstrates how to change the background color of suggestion box.

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

{% endtabs %}

![Dropdown background color](Dropdown_customization_images/drop_down_background_color.png)


## Drop-down placement 

The [SuggestionBoxPlacement](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~SuggestionBoxPlacement.html) property, defines the position of pop-up relative to the control. It contains three built-in options:

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
{% endtabs %}

![Top](Dropdown_customization_images/Top.png)

Drop-down list opening at the top.
{:.caption}


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
{% endtabs %}

![Bottom](Dropdown_customization_images/Bottom.png)

Drop-down list opening at the bottom.
{:.caption}

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
{% endtabs %}

![None](Dropdown_customization_images/None.png)

No drop-down list.
{:.caption}

## Setting the maximum height 

The maximum height of the suggestion box in the `Autocomplete` control can be changed using the [MaximumDropDownHeight](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~MaxDropDownHeight.html) property.

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

{% endtabs %}

![MaxDropDownHeight](Dropdown_customization_images/maximum_drop_down_height.png)

## Open the drop-down on focus 

Suggestion box can be shown whenever the control receives focus using the [ShowSuggestionsOnFocus](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~ShowSuggestionsOnFocus.html) property. At that time, suggestion list is the complete list of data source.

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

{% endtabs %}

![ShowSuggestionsOnFocus](Dropdown_customization_images/suggestion_on_focus.png)

## Open drop-down with a delay 

The [PopupDelay](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~PopupDelay.html) specifies the delay after, which the suggestion pop-up should open. 

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
{% endtabs %}



N> View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/Dropdown-customization) in GitHub