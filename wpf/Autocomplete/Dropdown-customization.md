---
layout: post
title: Dropdown Customization in WPF Autocomplete Control | Syncfusion®
description: Learn about dropdown customization support in the Syncfusion® WPF Autocomplete (SfTextBoxExt) control and more.
platform: WPF
control: SfTextBoxExt
documentation: ug
---

# Dropdown Customization in WPF Autocomplete (SfTextBoxExt)

The suggestion box is a drop-down list box, which displays the filtered suggestions inside a pop-up. This section explains the properties and customizations that deal with the drop-down list in the `AutoComplete` control.

## Customize the Background

The [DropDownBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_DropDownBackground) property is used to modify the background color of the suggestion box. The following code example demonstrates how to change the background color of the suggestion box.

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

## Drop-down Placement

The [SuggestionBoxPlacement](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SuggestionBoxPlacement) property defines the position of the pop-up relative to the control. It contains three built-in options:

1. Top
2. Bottom
3. None

The default value is `Bottom`.

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

## Setting the Maximum Height

The maximum height of the suggestion box in the AutoComplete control can be changed using the [MaxDropDownHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_MaxDropDownHeight) property.

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

## Open the Drop-down on Focus

The suggestion box can be shown whenever the control receives focus using the [ShowSuggestionsOnFocus](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_ShowSuggestionsOnFocus) property. At that time, the suggestion list is the complete list of the data source.

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

## Open Drop-down with a Delay

The [PopupDelay](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_PopupDelay) specifies the delay after which the suggestion pop-up should open.

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

## Customizing the Selected Item Background

The [SelectionBackgroundColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SelectionBackgroundColor) property is used to set the background color of the selected item in the suggestion box.

{% tabs %}

{% highlight xaml %}

        <editors:SfTextBoxExt
            Width="300"
            Height="40"
            HorizontalAlignment="Center"
            VerticalAlignment="Center"
            AutoCompleteMode="Suggest"
            AutoCompleteSource="{Binding Employees}"
            SearchItemPath="Name"
            SelectionBackgroundColor="Red"
            ShowDropDownButton="True" />

{% endhighlight %}
{% highlight c# %}

textBoxExt.SelectionBackgroundColor = new SolidColorBrush(Colors.Red);

{% endhighlight %}
{% endtabs %}

![Selected item background color](Dropdown_customization_images/SelectionBackgroundColor.png)

## Highlighting Matched Text in DropDown

`SfTextBoxExt` supports highlighting the first matched item when a dropdown is opened by setting the `AutoHighlightMatchedItem` property to true. The default value is false.

{% tabs %}

{% highlight xaml hl_lines="10" %}

    <Window.DataContext>
        <local:EmployeeViewModel/>
    </Window.DataContext>
    <Grid>
        <editors:SfTextBoxExt HorizontalAlignment="Center" 
                              VerticalAlignment="Center" 
                              Width="300"
                              Height="40"
                              SearchItemPath="Name"
                              AutoHighlightMatchedItem="True"
                              AutoCompleteMode="Suggest"
                              AutoCompleteSource="{Binding Employees}" />
     </Grid>

{% endhighlight %}

{% highlight c# hl_lines="9" %}

       SfTextBoxExt textBoxExt = new SfTextBoxExt();
       EmployeeViewModel viewModel = new EmployeeViewModel();
       this.DataContext = viewModel;
       textBoxExt.HorizontalAlignment = HorizontalAlignment.Center;
       textBoxExt.VerticalAlignment = VerticalAlignment.Center;
       textBoxExt.Width = 200;
       textBoxExt.Height = 40;
       textBoxExt.SearchItemPath = "Name";
       textBoxExt.AutoHighlightMatchedItem = true;
       textBoxExt.AutoCompleteMode = AutoCompleteMode.Suggest;
       textBoxExt.AutoCompleteSource = viewModel.Employees;
       this.Content = textBoxExt;

{% endhighlight %}

{% endtabs %}

![Highlighted Matched Item](Dropdown_customization_images/highlight_matched_item.png)

> **Note:** View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/Dropdown-customization) on GitHub
