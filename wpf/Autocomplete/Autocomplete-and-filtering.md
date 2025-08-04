---
layout: post
title: Autocomplete and Filtering in WPF Autocomplete Control | Syncfusion®
description: Learn about autocomplete and filtering support in Syncfusion® WPF Autocomplete (SfTextBoxExt) control and more.
platform: WPF
control: SfTextBoxExt
documentation: ug
---

# Autocomplete and Filtering in WPF Autocomplete (SfTextBoxExt)

The autocomplete functionality provides several modes of suggestions while typing. The suggested text can be appended to the original text or displayed in a drop-down list so that the searched item can be chosen based on the filtering option set.

## Autocomplete Source

The [SfTextBoxExt](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html) control can be populated with a predefined list of items bound to the [AutoCompleteSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_AutoCompleteSource) property. The data can be either a list of strings or custom data.


{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="300"
                      Height="40"
                      SearchItemPath="Name"
                      AutoCompleteMode="Suggest"
                      AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}
{% endtabs %}

For further details, refer to [Populating Autocomplete with Data](https://help.syncfusion.com/wpf/autocomplete/getting-started#populating-autocomplete-with-data).

![AutoCompleteSource](AutoComplete_and_filtering_images/AutoCompleteSource.png)

## Custom Data

The [SearchItemPath](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SearchItemPath) property specifies the property path by which the filtering is done when custom data is bound to the [AutoCompleteSource](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_AutoCompleteSource) property. This property defines the value to be displayed in the drop-down suggestion box.

{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="300"
                      Height="40"
                      SearchItemPath="Name"
                      AutoCompleteMode="Suggest"
                      AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}
{% highlight c# %}

textBoxExt.SearchItemPath = "Name";

{% endhighlight %}
{% endtabs %}

![SearchItemPath](AutoComplete_and_filtering_images/SearchItemPath.png)

## Customize Using the ItemTemplate

By default, the drop-down window lists the filtered items as text based on the [SearchItemPath](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SearchItemPath) property set for the data. The [AutoCompleteItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_AutoCompleteItemTemplate) property helps to decorate the filtered items with visual elements. The following code block explains how to add an image to the drop-down list items.

{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="400"
                      Height="40"
                      SearchItemPath="Name"
                      AutoCompleteMode="SuggestAppend"
                      AutoCompleteSource="{Binding Employees}" >
                      <editors:SfTextBoxExt.AutoCompleteItemTemplate>
                        <DataTemplate>
                            <StackPanel Orientation="Horizontal">
                                <Image Source="User.png" Margin="2" Stretch="Uniform" Width="12"/>
                                <TextBlock Text="{Binding Name}" Margin="5 2"/>
                            </StackPanel>
                        </DataTemplate>
                      </editors:SfTextBoxExt.AutoCompleteItemTemplate>
</editors:SfTextBoxExt>

{% endhighlight %}
{% endtabs %}

![ItemTemplate](AutoComplete_and_filtering_images/ItemTemplate.png)

## Filtering Options

The process of string comparison for filtering suggestions can be changed using the [SuggestionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_SuggestionMode) property. The default filtering strategy is "StartsWith" and is case-insensitive.

<table>
<tr>
<th>SuggestionMode</th>
<th>Description</th>
</tr>
<tr>
<td>None</td>
<td>
The control returns the entire collection without filtering.
</td>
</tr>
<tr>
<td>
StartsWith
</td>
<td>
Displays all matches that begins with the typed characters in the text field. This strategy is case-insensitive.
</td>
</tr>
<tr>
<td>
StartsWithCaseSensitive
</td>
<td>
Displays all matches that begins with the typed characters in the text field. This strategy is case-sensitive.
</td>
</tr>
<tr>
<td>
StartsWithOrdinal
</td>
<td>
The control returns all possible matches that begins with the typed text based on the OrdinalIgnoreCase.
</td>
</tr>
<tr>
<td>
StartsWithOrdinalCaseSensitive
</td>
<td>
The control returns all possible matches that begins with the typed text based on the Ordinal, which is case-sensitive.
</td>
</tr>
<tr>
<td>
Contains
</td>
<td>
Displays all matches that contains typed characters in the text field. This strategy is case-insensitive.
</td>
</tr>
<tr>
<td>
ContainsCaseSensitive
</td>
<td>
The control returns all possible matches that contains the typed text, which is culture and case-sensitive.
</td>
</tr>
<tr>
<td>
ContainsOrdinal
</td>
<td>
The control returns all possible matches that contains the typed text based on the OrdinalIgnoreCase.
</td>
</tr>
<tr>
<td>
ContainsOrdinalCaseSensitive
</td>
<td>
The control returns all possible matches that contains the typed text based on the Ordinal, which is case-sensitive.
</td>
</tr>
<tr>
<td>Equals</td>
<td>
Displays all words that completely matches the typed characters in the text field. This strategy is case-insensitive.
</td>
</tr>
<tr>
<td>
EqualsCaseSensitive
</td>
<td>
Displays all words that completely matches the typed characters in the text field. This strategy is case-sensitive.
</td>
</tr>
<tr>
<td>
EqualsOrdinal
</td>
<td>
The control returns all possible matches that equals the typed text based on the OrdinalIgnoreCase.
</td>
</tr>
<tr>
<td>
EqualsOrdinalCaseSensitive
</td>
<td>
The control returns all possible matches that equals the typed text based on the Ordinal, which is case-sensitive.
</td>
</tr>
<tr>
<td>
Custom
</td>
<td>
The control returns all possible matches based on the Filter property. Filter property is of type SuggestionPredicate. In the MyFilter method, filtration is done by checking whether the collection contains the typed text.
</td>
</tr>
<tr>
<td>
EndsWith
</td>
<td>
Displays all matches that ends with the typed characters in the text field. This strategy is case-insensitive.
</td>
</tr>
<tr>
<td>
EndsWithCaseSensitive
</td>
<td>
Displays all matches that ends with the typed characters in the text field. This strategy is case-sensitive.
</td>
</tr>
<tr>
<td>
EndsWithOrdinal
</td>
<td>
The control returns all possible matches ending with the typed text based on the OrdinalIgnoreCase.
</td>
</tr>
<tr>
<td>
EndsWithOrdinalCaseSensitive
</td>
<td>
The control returns all possible matches ending with the typed text based on the Ordinal, which is case-sensitive.
</td>
</tr>
</table>


{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="400"
                      Height="40"
                      SearchItemPath="Name"
                      SuggestionMode="Contains"
                      AutoCompleteMode="Suggest"
                      AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}
{% highlight c# %}

textBoxExt.SuggestionMode = SuggestionMode.Contains;

{% endhighlight %}
{% endtabs %}

![Contains](AutoComplete_and_filtering_images/Contains.png)

### Custom

Filter items in the suggestion list based on the user's custom search. This allows you to apply typo tolerance functionality to the control.

![Custom filter](AutoComplete_and_filtering_images/Custom.png)


{% tabs %}

{% highlight xaml %}

    <Window x:Class="AutoCompleteWPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:AutoCompleteWPF" 
        xmlns:editors="http://schemas.syncfusion.com/wpf" xmlns:ListCollection="http://schemas.microsoft.com/netfx/2009/xaml/presentation" xmlns:sys="clr-namespace:System;assembly=mscorlib"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <StackPanel>
        <editors:SfTextBoxExt x:Name="autoComplete" 
                               Width="300"
                               Height="40"
                               HorizontalAlignment="Center"
                               VerticalAlignment="Center"
                               AutoCompleteMode="Suggest"
                               SuggestionMode="Custom">
            <editors:SfTextBoxExt.AutoCompleteSource>
                <x:Array Type="{x:Type sys:String}">
                    <sys:String>Albania</sys:String>
                    <sys:String>Algeria</sys:String>
                    <sys:String>American Samoa</sys:String>
                    <sys:String>Andorra</sys:String>
                    <sys:String>Angola</sys:String>
                    <sys:String>Anguilla</sys:String>
                </x:Array>
            </editors:SfTextBoxExt.AutoCompleteSource>
        </editors:SfTextBoxExt>
    </StackPanel>
</Window>


{% endhighlight %}

{% highlight c# %}

    using System;
    using System.Windows;

    namespace AutoCompleteWPF
    {
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            autoComplete.Filter = ContainingSpaceFilter;
        }

         public bool ContainingSpaceFilter(string search, object item)
        {
            string text = item.ToString().ToLower();
            if (item != null)
            {
                try
                {
                    var split = search.Split(' ');
                    foreach (var results in split)
                    {
                        if (!text.Contains(results.ToLower()))
                        {
                            return true; 
                        }
                        else
                            return false;
                    }
                    return true;
                }
                catch (Exception)
                {
                    return (text.Contains(search));
                }
            }
            else
                return false;
        }
    }
    }

{% endhighlight %}

{% endtabs %}

## Prefix Character Constraint

Instead of displaying a suggestion list on every character entry, matches can be filtered and displayed after a few character entries. This can be done using the [MinimumPrefixCharacter](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_MinimumPrefixCharacters) property. By default, the constraint is set for each character entry.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="300"
                      Height="40"
                      SearchItemPath="Name"
                      AutoCompleteMode="Suggest"
                      MinimumPrefixCharacters="2"
                      AutoCompleteSource="{Binding Employees}" />
     
{% endhighlight %}
{% highlight c# %}

textBoxExt.MinimumPrefixCharacters = 2;

{% endhighlight %}

{% endtabs %}

![Minimum Prefix Length](AutoComplete_and_filtering_images/MinimumPrefixCharacters.png)

## Working with Case Sensitivity

The [IgnoreCase](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_IgnoreCase) option allows the control to filter the suggestions by ignoring the case. The default value is false.

{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="400"
                      Height="40"
                      SearchItemPath="Name"
                      IgnoreCase="True"
                      AutoCompleteMode="Suggest"
                      AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}
{% highlight c# %}

textBoxExt.IgnoreCase = true;

{% endhighlight %}
{% endtabs %}

![Ignore Case](AutoComplete_and_filtering_images/IgnoreCase.png)

## Showing Image in Token and Drop-down

To display an image in the token, use the [ImageMemberPath](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_ImageMemberPath) property.

> **Note:** This feature is applicable only for MultiSelectMode with Token mode.

To display an image for each drop-down item, a custom template can be assigned to [AutoCompleteItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_AutoCompleteItemTemplate).

{% tabs %}
{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Left"
                      AutoCompleteMode="Suggest"
                      SearchItemPath="Name"
                      ImageMemberPath="Image"
                      MultiSelectMode="Token" 
                      TokensWrapMode="None"
                      Height="40"
                      AutoCompleteSource="{Binding Employees}"
                      VerticalAlignment="Center"
                      Width="200">
            <editors:SfTextBoxExt.AutoCompleteItemTemplate>
                <DataTemplate>
                    <StackPanel Orientation="Horizontal" Height="40">
                        <Image Source="{Binding Image}" Margin="2" Height="35" Stretch="Uniform" Width="35"/>
                        <StackPanel  Margin="2"
                                            Orientation="Vertical">
                            <TextBlock Text="{Binding Name}" Margin="4,2,4,0" FontSize="12" Foreground="Black"/>
                            <TextBlock Text="{Binding Email}" Margin="4,1,2,2" FontSize="10" Foreground="Gray"/>
                        </StackPanel>
                    </StackPanel>
                </DataTemplate>
            </editors:SfTextBoxExt.AutoCompleteItemTemplate>
</editors:SfTextBoxExt>

{% endhighlight %}

{% endtabs %}

![ImageMemberPath](AutoComplete_and_filtering_images/ImageMemberPath.png)

> **Note:** View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-autocomplete) on GitHub

## Display a Message When Suggestions are Empty

When the entered item is not in the suggestion list, AutoComplete displays a text indicating that there are no search results found. The text for this message can be customized using the [NoResultsFoundTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_NoResultsFoundTemplate) property.

{% tabs %}
{% highlight xaml %}
       
<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Height="40"
                      Width="400"
                      SearchItemPath="Name"
                      AutoCompleteMode="Suggest"
                      AutoCompleteSource="{Binding Employees}">
            <editors:SfTextBoxExt.NoResultsFoundTemplate>
                <DataTemplate>
                    <Label Content="No Results Found" HorizontalAlignment="Center" VerticalAlignment="Center"/>
                </DataTemplate>
            </editors:SfTextBoxExt.NoResultsFoundTemplate>
</editors:SfTextBoxExt>

{% endhighlight %}
{% endtabs %}

![NoResultsFoundTemplate](AutoComplete_and_filtering_images/NoResultsFoundTemplate.png)

## Restricting the Maximum Items Filtered

The [MaximumSuggestionsCount](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_MaximumSuggestionsCount) property is used to restrict the number of suggestions displayed in the suggestion box.

{% tabs %}
{% highlight xaml %}
       
        <editors:SfTextBoxExt
            Width="300"
            Height="40"
            HorizontalAlignment="Center"
            VerticalAlignment="Center"
            AutoCompleteMode="Suggest"
            AutoCompleteSource="{Binding Employees}"
            MaximumSuggestionsCount="3"
            SearchItemPath="Name" />

{% endhighlight %}

{% highlight c# %}

textBoxExt.MaximumSuggestionsCount = 3;

{% endhighlight %}
{% endtabs %}

![MaximumSuggestionsCount](AutoComplete_and_filtering_images/MaximumSuggestionsCount.png)

> **Note:** View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-autocomplete-and-filtering) on GitHub
