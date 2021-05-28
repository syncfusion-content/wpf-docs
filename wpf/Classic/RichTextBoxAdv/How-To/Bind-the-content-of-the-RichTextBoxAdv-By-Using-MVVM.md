---
layout: post
title: Bind the content in RichTextBoxAdv By Using MVVM | Syncfusion
description: Learn here all about Bind the content of the RichTextBoxAdv By Using MVVM support in Syncfusion WPF RichTextBoxAdv (Classic) control and more.
platform: wpf
control: RichTextBoxAdv
 documentation: ug
---

# Bind the content of the WPF RichTextBoxAdv (Classic) By Using MVVM

You can bind the content of a RichTextBoxAdv control in XAML (designer) by defining a MVVM extension for the XAMLText or HTMLText property. You cannot update the XAMLText or HTMLText property dynamically by modifying content in the RichTextBoxAdv, but you can update it by accessing the XAMLText or HTMLText property (In Getter method).

You can explicitly update the XAMLText or HTMLText property to view model for content binding by using the LayoutUpdated event that is triggered when content is modified in the RichTextBoxAdv control.

The following code example illustrates defining MVVM extension for the XAMLText property of the RichTextBoxAdv control.

{% tabs %}
{% highlight xaml %}






<syncfusion:RichTextBoxAdv x:Name="richTextBoxAdv" XAMLText="{Binding DescriptionXaml}" />

{% endhighlight %}


{% highlight C# %}





/// <summary>

/// Handles the LayoutUpdated event of the richTextBoxAdv control.

/// </summary>

/// <param name="sender">The source of the event.</param>

/// <param name="e">The <see cref="EventArgs"/> instance containing the event data.</param>

void richTextBoxAdv_LayoutUpdated(object sender, EventArgs e)

{

    if ((this.DataContext as ViewModel).XamlContent != richTextBoxAdv.XAMLText)

        //Updates the XAMLText for changes made in RichTextBoxAdv to ViewModel.

        (this.DataContext as ViewModel).XamlContent = richTextBoxAdv.XAMLText;

}

/// <summary>

/// Sample View Model class

/// </summary>

public class ViewModel : INotifyPropertyChanged

{

    private String descriptionXaml;

    /// <summary>

    /// Initializes a new instance of the <see cref="ViewModel"/> class.

    /// </summary>

    public ViewModel()

    {

      // Sample description xaml.

DescriptionXaml = "<RichText:DocumentAdv xmlns=\"http://schemas.microsoft.com/winfx/2006/xaml/presentation\" xmlns:RichText=\"clr-namespace:Syncfusion.Windows.Tools.Controls;assembly=Syncfusion.RichTextBoxAdv.Silverlight\" >\r\n<RichText:SectionAdv><RichText:ParagraphAdv ListType=\"None\" TextAlignment=\"Left\" LeftIndent=\"0\" RightIndent=\"0\" BeforeSpacing=\"0\" AfterSpacing=\"13\" >\r\n<RichText:SpanAdv Text=\"RichTextBoxAdv is a control using which you can format the text, align and indent the paragraph, and display the content in pages or web layout mode.\" FontStyle=\"Normal\" Baseline=\"Normal\" HighlightColor=\"#00000000\" Foreground=\"#FF000000\" FontSize=\"12\" FontFamily=\"Segoe UI\" FontWeight=\"Normal\" >\r\n</RichText:SpanAdv>\r\n</RichText:ParagraphAdv>\r\n</RichText:SectionAdv></RichText:DocumentAdv>";

    }

    /// <summary>

    /// Gets or sets the description xaml.

    /// </summary>

    /// <value>

    /// The description xaml.

    /// </value>

    public String DescriptionXaml

    {

        get

        {

            return descriptionXaml;

        }

        set

        {

            descriptionXaml = value;

            if (PropertyChanged != null)

                PropertyChanged(this, new PropertyChangedEventArgs("DescriptionXaml"));

        }

    }

    /// <summary>

    /// Gets or sets the content of the xaml.

    /// </summary>

    /// <value>

    /// The content of the xaml.

    /// </value>

    internal String XamlContent

    {

        get

        {

            return descriptionXaml;

        }

        set

        {

            descriptionXaml = value;

        }

    }

    /// <summary>

    /// Occurs when a property value changes.

    /// </summary>

    public event PropertyChangedEventHandler PropertyChanged;

}

{% endhighlight %}
{% endtabs %}

## Sample

To view a sample on binding the XAMLText property of RichTextBoxAdv control by using MVVM Framework, see [Sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MVVM_Sample-422358601).



