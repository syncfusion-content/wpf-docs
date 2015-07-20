---
layout: post
title: Bind-the-content-of-the-RichTextBoxAdv-By-Using-MVVM
description: bind the content of the richtextboxadv by using mvvm
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

### Bind the content of the RichTextBoxAdv By Using MVVM

You can bind the content of a RichTextBoxAdv control in XAML (designer) by defining a MVVM extension for the XAMLText or HTMLText property. You cannot update the XAMLText or HTMLText property dynamically by modifying content in the RichTextBoxAdv, but you can update it by accessing the XAMLText or HTMLText property (In Getter method).

You can explicitly update the XAMLText or HTMLText property to view model for content binding by using the LayoutUpdated event that is triggered when content is modified in the RichTextBoxAdv control.

The following code example illustrates defining MVVM extension for the XAMLText property of the RichTextBoxAdv control.

[XAML]



&lt;syncfusion:RichTextBoxAdv x:Name="richTextBoxAdv" XAMLText="{Binding DescriptionXaml}" /&gt;





[C#]



/// &lt;summary&gt;

/// Handles the LayoutUpdated event of the richTextBoxAdv control.

/// &lt;/summary&gt;

/// <param name="sender">The source of the event.&lt;/param&gt;

/// <param name="e">The &lt;see cref="EventArgs"/&gt; instance containing the event data.&lt;/param&gt;

void richTextBoxAdv_LayoutUpdated(object sender, EventArgs e)

{

    if ((this.DataContext as ViewModel).XamlContent != richTextBoxAdv.XAMLText)

        //Updates the XAMLText for changes made in RichTextBoxAdv to ViewModel.

        (this.DataContext as ViewModel).XamlContent = richTextBoxAdv.XAMLText;

}

/// &lt;summary&gt;

/// Sample View Model class

/// &lt;/summary&gt;

public class ViewModel : INotifyPropertyChanged

{

    private String descriptionXaml;

    /// &lt;summary&gt;

    /// Initializes a new instance of the &lt;see cref="ViewModel"/&gt; class.

    /// &lt;/summary&gt;

    public ViewModel()

    {

      // Sample description xaml.

DescriptionXaml = "&lt;RichText:DocumentAdv xmlns=\"http://schemas.microsoft.com/winfx/2006/xaml/presentation\" xmlns:RichText=\"clr-namespace:Syncfusion.Windows.Tools.Controls;assembly=Syncfusion.RichTextBoxAdv.Silverlight\" &gt;\r\n<RichText:SectionAdv>&lt;RichText:ParagraphAdv ListType=\"None\" TextAlignment=\"Left\" LeftIndent=\"0\" RightIndent=\"0\" BeforeSpacing=\"0\" AfterSpacing=\"13\" &gt;\r\n<RichText:SpanAdv Text=\"RichTextBoxAdv is a control using which you can format the text, align and indent the paragraph, and display the content in pages or web layout mode.\" FontStyle=\"Normal\" Baseline=\"Normal\" HighlightColor=\"#00000000\" Foreground=\"#FF000000\" FontSize=\"12\" FontFamily=\"Segoe UI\" FontWeight=\"Normal\" >\r\n</RichText:SpanAdv>\r\n</RichText:ParagraphAdv>\r\n</RichText:SectionAdv>&lt;/RichText:DocumentAdv&gt;";

    }

    /// &lt;summary&gt;

    /// Gets or sets the description xaml.

    /// &lt;/summary&gt;

    /// &lt;value&gt;

    /// The description xaml.

    /// &lt;/value&gt;

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

    /// &lt;summary&gt;

    /// Gets or sets the content of the xaml.

    /// &lt;/summary&gt;

    /// &lt;value&gt;

    /// The content of the xaml.

    /// &lt;/value&gt;

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

    /// &lt;summary&gt;

    /// Occurs when a property value changes.

    /// &lt;/summary&gt;

    public event PropertyChangedEventHandler PropertyChanged;

}



Sample

To view a sample on binding the XAMLText property of RichTextBoxAdv control by using MVVM framework, see [http://www.syncfusion.com/downloads/support/directtrac/117738/Sample-1166502320.zip](http://www.syncfusion.com/downloads/support/directtrac/117738/Sample-1166502320.zip).



