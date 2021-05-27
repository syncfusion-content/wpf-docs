---
title: Dialogs in WPF RichTextBox control | Syncfusion
description: Learn here all about Dialogs support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: dialogs
---
# Dialogs in WPF RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv provides support for the following built-in dialogs similar to Microsoft Word application.

* Font Dialog

* Paragraph Dialog

* List Dialog

* Insert Table Dialog

* Insert Hyperlink Dialog

* Find and Replace Dialog

* Password Dialog

* Table Properties Dialog

* Table Options Dialog

* Cell Options Dialog

* Borders and Shading Dialog

* Styles Dialog

## UI Commands for accessing dialogs

The following code example demonstrates how to show the built-in dialogs in SfRichTextBoxAdv through command binding.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the ShowFontDialogCommand -->
<Button Content="Font" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowFontDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowParagraphDialogCommand -->
<Button Content="Paragraph" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowParagraphDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowListDialogCommand -->
<Button Content="List" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowListDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowInsertTableDialogCommand -->
<Button Content="Insert Table" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowInsertTableDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowHyperlinkDialogCommand -->
<Button Content="Hyperlink" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowHyperlinkDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowFindAndReplaceDialogCommand -->
<Button Content="Find and Replace" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowFindAndReplaceDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowEncryptDocumentDialogCommand -->
<Button Content="Encrypt Document" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowEncryptDocumentDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowTableDialogCommand -->
<Button Content="Table Properties" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowTableDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowTableOptionsDialogCommand -->
<Button Content="Table Options" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowTableOptionsDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowCellOptionsDialogCommand -->
<Button Content="Cell Options" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowCellOptionsDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowBordersAndShadingDialogCommand -->
<Button Content="Borders and Shading" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowBordersAndShadingDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowStyleDialogCommand -->
<Button Content="Create style" Command="Syncfusion:SfRichTextBoxAdv.ShowStyleDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowStylesDialogCommand -->
<Button Content="Modify style" Command="Syncfusion:SfRichTextBoxAdv.ShowStylesDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
{% endhighlight %}

{% endtabs %}


## Customizing dialogs

This section describes how to create custom window for the dialogs of SfRichTextBoxAdv.
The following code example demonstrates how to design custom window for the font dialog of SfRichTextBoxAdv.

{% tabs %}
{% highlight xaml %}
<Window x:Class="DocumentEditor.FontWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:DocumentEditor"
        mc:Ignorable="d"
        xmlns:Syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:System="clr-namespace:System;assembly=mscorlib"
        Title="FontWindow" Height="530" Width="500">
    <Grid>
        <Syncfusion:FontDialog Name="fontDialog"></Syncfusion:FontDialog>
    </Grid>
</Window>
{% endhighlight %}
{% highlight c# %}
public partial class FontWindow : Window
    {
        public FontWindow(SfRichTextBoxAdv rte)
        {
            InitializeComponent();
            fontDialog.DataContext = rte;
            this.Loaded += FontWindow_Loaded;
        }
        /// <summary>
        /// Called when the font window is loaded.
        /// </summary>
        /// <param name="sender"></param>
        /// <param name="e"></param>
        private void FontWindow_Loaded(object sender, RoutedEventArgs e)
        {
            //Hooks the event for cancel button of font dialog.
            FontDialog font = VisualUtils.FindDescendant(sender as FontWindow, typeof(FontDialog)) as FontDialog;
            Button cancelButton = font.Template.FindName("PART_CancelButton", font as FrameworkElement) as Button;
            if (cancelButton != null)
            {
                cancelButton.Click += CancelButton_Click;
            }
            Button applybutton = font.Template.FindName("PART_ApplyFontFormatButton", font as FrameworkElement) as Button;
            if (applybutton != null)
            {
                applybutton.Click += Applybutton_Click;
            }
        }

        private void Applybutton_Click(object sender, RoutedEventArgs e)
        {
            this.Hide();//Hides the window.
        }

        protected override void OnClosing(CancelEventArgs e)
        {
            //Hiding the window on close button.
            base.OnClosing(e);
            Hide();
            e.Cancel = true;  
        }
        /// <summary>
        /// Called when the cancel button is clicked.
        /// </summary>
        /// <param name="sender"></param>
        /// <param name="e"></param>
        private void CancelButton_Click(object sender, RoutedEventArgs e)
        {
            this.Hide();//hides the window.
        }
    }
{% endhighlight %}
{% highlight VB %}
Public Partial Class FontWindow
	Inherits Window
	Public Sub New(rte As SfRichTextBoxAdv)
		InitializeComponent()
		fontDialog.DataContext = rte
		AddHandler this.Loaded, AddressOf FontWindow_Loaded
	End Sub
''' <summary>
''' Called when the font window is loaded.
''' </summary>
''' <param name="sender"></param>
''' <param name="e"></param>
Private Sub FontWindow_Loaded(sender As Object, e As RoutedEventArgs)
	'Hooks the event for cancel button of font dialog.
	Dim font As FontDialog = TryCast(VisualUtils.FindDescendant(TryCast(sender, FontWindow), GetType(FontDialog)), FontDialog)
	Dim cancelButton As Button = TryCast(font.Template.FindName("PART_CancelButton", TryCast(font, FrameworkElement)), Button)
	If cancelButton IsNot Nothing Then
		AddHandler cancelButton.Click, AddressOf CancelButton_Click 
	End If
	Dim applybutton As Button = TryCast(font.Template.FindName("PART_ApplyFontFormatButton", TryCast(font, FrameworkElement)), Button)
	If applybutton IsNot Nothing Then
		Addhandler applybutton.Click, AddressOf Applybutton_Click
	End If
End Sub

Private Sub Applybutton_Click(sender As Object, e As RoutedEventArgs)
	Me.Hide()
	'Hides the window.
End Sub

Protected Overrides Sub OnClosing(e As CancelEventArgs)
	'Hiding the window on close button.
	MyBase.OnClosing(e)
	Hide()
	e.Cancel = True
End Sub
''' <summary>
''' Called when the cancel button is clicked.
''' </summary>
''' <param name="sender"></param>
''' <param name="e"></param>
Private Sub CancelButton_Click(sender As Object, e As RoutedEventArgs)
	Me.Hide()
	'hides the window.
End Sub
End Class
{% endhighlight %}
{% endtabs %}

N> After creating custom dialog window, you have to set the SfRichTextBoxAdv instance as DataContext of the dialog.

The following code example demonstrates how to deploy the created font dialog window in your application.

{% tabs %}
{% highlight xaml %}
<Syncfusion:RibbonWindow x:Class="DocumentEditor.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:DocumentEditor"
        mc:Ignorable="d"
        xmlns:Syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:System="clr-namespace:System;assembly=mscorlib"
        xmlns:RichTextBoxAdv="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.WPF"
        Title="MainWindow" Width="1087" Height="635" Syncfusion:SkinStorage.VisualStyle="Office2013">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <Button Content="Font Dialog" Height="50" Width="200" Click="Button_Click"></Button>
        <Syncfusion:SfRichTextBoxAdv x:Name="richTextBoxAdv" Background="#F1F1F1" DocumentTitle="RichTextBoxAdv" LayoutType="Pages" AcceptsTab="True" Grid.Row="1"></Syncfusion:SfRichTextBoxAdv>
    </Grid>
</Syncfusion:RibbonWindow>
{% endhighlight %}
{% highlight c# %}
public partial class MainWindow : RibbonWindow
    {
        public FontWindow fontWindow { get; set; }

        public MainWindow()
        {
            InitializeComponent();
            fontWindow = new FontWindow(richTextBoxAdv);
            this.Unloaded += MainWindow_Unloaded;
        }

        private void MainWindow_Unloaded(object sender, RoutedEventArgs e)
        {
            fontWindow.Close();//closing the font window.
        }

        private void Button_Click(object sender, RoutedEventArgs e)
        {
            fontWindow.Show();//showing the font window.
        }
    }
    
{% endhighlight %}
{% highlight VB %}
Public Partial Class MainWindow
	Inherits RibbonWindow
	Public Property fontWindow() As FontWindow
		Get
			Return m_fontWindow
		End Get
		Set
			m_fontWindow = Value
		End Set
	End Property
	Private m_fontWindow As FontWindow

	Public Sub New()
		InitializeComponent()
		fontWindow = New FontWindow(richTextBoxAdv)
		AddHandler this.Unloaded, AddressOf MainWindow_Unloaded
	End Sub
	Private Sub MainWindow_Unloaded(sender As Object, e As RoutedEventArgs)
	fontWindow.Close()
	'closing the font window.
End Sub

Private Sub Button_Click(sender As Object, e As RoutedEventArgs)
	fontWindow.Show()
	'showing the font window.
End Sub
End Class


{% endhighlight %}
{% endtabs %}
