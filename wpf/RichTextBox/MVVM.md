---
title: MVVM in WPF RichTextBox control | Syncfusion
description: Learn here all about MVVM support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: mvvm
---
# MVVM in WPF RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv control can be used with Model-View-View Model (MVVM) pattern. This section will demonstrate how to use the SfRichTextBoxAdv control with MVVM pattern.

## Creating a View Model

The following code example demonstrates how to implement a view model class that contains properties to preserve the description about some of the animals and the animal that is selected for discussion. Whenever the animal chosen for discussion is changed, previously chosen animal description is updated to the database and newly chosen animal description is updated to the text property.
{% tabs %}
{% highlight c# %}
/// <summary>
/// Represents the view model class.
/// </summary>
public class ViewModel : INotifyPropertyChanged
{
    #region Field
    private string animal;
    private string text;
    Dictionary<string, string> animals = null;
    bool skipUpdating = false;
    #endregion

    #region Properties
    /// <summary>
    /// Gets or sets the animal.
    /// </summary>
    /// <value>
    /// The document title.
    /// </value>
    public string Animal
    {
        get
        {
            return animal;
        }
        set
        {
            animal = value;
            NotifyPropertyChanged("Animal");
        }
    }
    /// <summary>
    /// Gets the animals.
    /// </summary>
    /// <value>
    /// The animals.
    /// </value>
    public ICollection<string> Animals
    {
        get
        {
            return animals.Keys;
        }
    }
    /// <summary>
    /// Gets or sets the Text.
    /// </summary>
    /// <value>
    /// The document.
    /// </value>
    public string Text
    {
        get
        {
            return text;
        }
        set
        {
            text = value;
            NotifyPropertyChanged("Text");
        }
    }
    #endregion

    #region Event
    public event PropertyChangedEventHandler PropertyChanged;
    #endregion

    #region Constructor
    /// <summary>
    /// Initializes a new instance of the <see cref="ViewModel"/> class.
    /// </summary>
    public ViewModel()
    {
        Initialize();
    }
    #endregion

    #region Implementation
    /// <summary>
    /// Handles initialization.
    /// </summary>
    private void Initialize()
    {
        animals = new Dictionary<string, string>();

        animals.Add("Tiger", "The tiger is the largest cat species, reaching a total body length of up to 3.38 m over curves and exceptionally weighing up to 388.7 kg in the wild.");
        animals.Add("Lion", "The lion is one of the strongest animal. It is also known as the king of jungles.");
        animals.Add("Panda", "The giant panda, also known as panda bear or simply panda, is a bear native to south central China. It is easily recognized by the large, distinctive black patches around its eyes, over the ears, and across its round body.");
        animals.Add("Beer", "Bears are mammals and are classified as dog like carnivorous.");
        animals.Add("Deer", "Deer are the ruminant mammals. Species in the family include the white-tailed deer, mule deer, elk, moose, red deer, reindeer, fallow deer, roe deer.");

        Animal = "Lion";
    }
    /// <summary>
    /// Notifies the property changed.
    /// </summary>
    /// <param name="propertyName">Name of the property.</param>
    private void NotifyPropertyChanged(string propertyName)
    {
        if (PropertyChanged != null)
            PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
        // Updates the text when the animal changes (reflects the view).
        if (propertyName == "Animal")
        {
            skipUpdating = true;
            Text = animals[animal];
            skipUpdating = false;
        }
        // Updates the document content, when changes done in view.
        if (propertyName == "Text" && !skipUpdating)
            animals[Animal] = Text;
    }
    #endregion
}



{% endhighlight %}
{% highlight VB %}
''' <summary>
''' Represents the view model class.
''' </summary>
Public Class ViewModel
	Implements INotifyPropertyChanged
	#Region "Field"
	Private m_animal As String
	Private m_text As String
	Private m_animals As Dictionary(Of String, String) = Nothing
	Private skipUpdating As Boolean = False
	#End Region

	#Region "Properties"
	''' <summary>
	''' Gets or sets the animal.
	''' </summary>
	''' <value>
	''' The document title.
	''' </value>
	Public Property Animal() As String
		Get
			Return m_animal
		End Get
		Set
			m_animal = value
			NotifyPropertyChanged("Animal")
		End Set
	End Property
	''' <summary>
	''' Gets the animals.
	''' </summary>
	''' <value>
	''' The animals.
	''' </value>
	Public ReadOnly Property Animals() As ICollection(Of String)
		Get
			Return m_animals.Keys
		End Get
	End Property
	''' <summary>
	''' Gets or sets the Text.
	''' </summary>
	''' <value>
	''' The document.
	''' </value>
	Public Property Text() As String
		Get
			Return m_text
		End Get
		Set
			m_text = value
			NotifyPropertyChanged("Text")
		End Set
	End Property
	#End Region

	#Region "Event"
	Public Event PropertyChanged As PropertyChangedEventHandler
	#End Region

	#Region "Constructor"
	''' <summary>
	''' Initializes a new instance of the <see cref="ViewModel"/> class.
	''' </summary>
	Public Sub New()
		Initialize()
	End Sub
	#End Region

	#Region "Implementation"
	''' <summary>
	''' Handles initialization.
	''' </summary>
	Private Sub Initialize()
		m_animals = New Dictionary(Of String, String)()

	    m_animals.Add("Tiger", "The tiger is the largest cat species, reaching a total body length of up to 3.38 m over curves and exceptionally weighing up to 388.7 kg in the wild.");
        m_animals.Add("Lion", "The lion is one of the strongest animal. It is also known as the king of jungles.");
        m_animals.Add("Panda", "The giant panda, also known as panda bear or simply panda, is a bear native to south central China. It is easily recognized by the large, distinctive black patches around its eyes, over the ears, and across its round body.");
        m_animals.Add("Beer", "Bears are mammals and are classified as dog like carnivorous.");
        m_animals.Add("Deer", "Deer are the ruminant mammals. Species in the family include the white-tailed deer, mule deer, elk, moose, red deer, reindeer, fallow deer, roe deer.");

		Animal = "Lion"
	End Sub
	''' <summary>
	''' Notifies the property changed.
	''' </summary>
	''' <param name="propertyName">Name of the property.</param>
	Private Sub NotifyPropertyChanged(propertyName As String)
		RaiseEvent PropertyChanged(Me, New PropertyChangedEventArgs(propertyName))
		' Updates the text when the animal changes (reflects the view).
		If propertyName = "Animal" Then
			skipUpdating = True
			Text = m_animals(m_animal)
			skipUpdating = False
		End If
		' Updates the document content, when changes done in view.
		If propertyName = "Text" AndAlso Not skipUpdating Then
			m_animals(Animal) = Text
		End If
	End Sub
	#End Region
End Class
{% endhighlight %}
{% endtabs %}

## Implementing extension class for SfRichTextBoxAdv

The following code example demonstrates how to implement an extension class for SfRichTextBoxAdv with dependency property that supports two way binding.
{% tabs %}
{% highlight c# %}
/// <summary>
/// Represents the extension class for SfRichTextBoxAdv.
/// </summary>
public class SfRichTextBoxAdvExtension : SfRichTextBoxAdv
{
    #region Fields
    bool skipUpdating = false;
    #endregion

    #region Properties
    /// <summary>
    /// Gets or Sets the text.
    /// </summary>
    public string Text
    {
        get
        {
            return (string)GetValue(TextProperty);
        }
        set
        {
            SetValue(TextProperty, value);
        }
    }
    #endregion

    #region Constructor
    /// <summary>
    /// Initializes the instance of SfRichTextBoxAdvExtension class.
    /// </summary>
    public SfRichTextBoxAdvExtension()
    {
        // Wires the ContentChanged event.
        this.ContentChanged += RicTextBoxAdv_ContentChanged;
    }
    #endregion

    #region Static Dependency Properties
    /// <summary>
    /// Using as a backing store for Text dependency property to enable styling, animation etc.
    /// </summary>
    public static readonly DependencyProperty TextProperty = DependencyProperty.Register("Text", typeof(string), typeof(SfRichTextBoxAdvExtension), new PropertyMetadata(string.Empty, new PropertyChangedCallback(OnTextChanged)));
    #endregion

    #region Static Events
    /// <summary>
    /// Called when text changed.
    /// </summary>
    /// <param name="obj"></param>
    /// <param name="e"></param>
    private static void OnTextChanged(DependencyObject obj, DependencyPropertyChangedEventArgs e)
    {
        SfRichTextBoxAdvExtension richTextBox = (SfRichTextBoxAdvExtension)obj;
        //Update the document with the Text.
        richTextBox.UpdateDocument((string)e.NewValue);
    }
    #endregion

    #region Events
    /// <summary>
    /// Called when content changes in SfRichTextBoxAdv.
    /// </summary>
    /// <param name="obj"></param>
    /// <param name="args"></param>
    void RicTextBoxAdv_ContentChanged(object obj, ContentChangedEventArgs args)
    {
        if (this.Document != null)
        {
            // To skip internal updation of document on setting Text property.
            skipUpdating = true;
            Stream stream = new MemoryStream();
            // Saves the document's text into a Stream.
            this.Save(stream, FormatType.Txt);
            stream.Position = 0;
            // Reads the text from the stream.
            using (StreamReader reader = new StreamReader(stream))
            {
                this.Text = reader.ReadToEnd();
            }
            skipUpdating = false;
        }
    }
    #endregion

    #region Implementation
    /// <summary>
    /// Updates the document.
    /// </summary>
    /// <param name="text"></param>
    private void UpdateDocument(string text)
    {
        // If text property is set internally means, skip updating the document.
        if (!skipUpdating && !string.IsNullOrEmpty(text))
        {
            Stream stream = new MemoryStream();
            // Convert the text to byte array.
            byte[] bytes = Encoding.UTF8.GetBytes(text);
            // Writes the byte array to stream.
            stream.Write(bytes, 0, bytes.Length);
            stream.Position = 0;
            //Load the stream.
            Load(stream, FormatType.Txt);
        }
    }
    /// <summary>
    /// Disposes the instance.
    /// </summary>
    public new void Dispose()
    {
        this.ContentChanged -= RicTextBoxAdv_ContentChanged;
        ClearValue(TextProperty);
        base.Dispose();
    }
    #endregion
}


{% endhighlight %}
{% highlight VB %}
''' <summary>
''' Represents the extension class for SfRichTextBoxAdv.
''' </summary>
Public Class SfRichTextBoxAdvExtension
	Inherits SfRichTextBoxAdv
	#Region "Fields"
	Private skipUpdating As Boolean = False
	#End Region

	#Region "Properties"
	''' <summary>
	''' Gets or Sets the text.
	''' </summary>
	Public Property Text() As String
		Get
			Return DirectCast(GetValue(TextProperty), String)
		End Get
		Set
			SetValue(TextProperty, value)
		End Set
	End Property
	#End Region
	
	#Region "Constructor"
''' <summary>
''' Initializes the instance of SfRichTextBoxAdvExtension class.
''' </summary>
Public Sub New()
	' Wires the ContentChanged event.
	AddHandler this.ContentChanged, AddressOf RicTextBoxAdv_ContentChanged
End Sub
#End Region

#Region "Static Dependency Properties"
''' <summary>
''' Using as a backing store for Text dependency property to enable styling, animation etc.
''' </summary>
Public Shared ReadOnly TextProperty As DependencyProperty = DependencyProperty.Register("Text", GetType(String), GetType(SfRichTextBoxAdvExtension), New PropertyMetadata(String.Empty, New PropertyChangedCallback(OnTextChanged)))
#End Region

#Region "Static Events"
''' <summary>
''' Called when text changed.
''' </summary>
''' <param name="obj"></param>
''' <param name="e"></param>
Private Shared Sub OnTextChanged(obj As DependencyObject, e As DependencyPropertyChangedEventArgs)
	Dim richTextBox As SfRichTextBoxAdvExtension = DirectCast(obj, SfRichTextBoxAdvExtension)
	'Update the document with the Text.
	richTextBox.UpdateDocument(DirectCast(e.NewValue, String))
End Sub
#End Region

#Region "Events"
''' <summary>
''' Called when content changes in SfRichTextBoxAdv.
''' </summary>
''' <param name="obj"></param>
''' <param name="args"></param>
Private Sub RicTextBoxAdv_ContentChanged(obj As Object, args As ContentChangedEventArgs)
	If Me.Document IsNot Nothing Then
		' To skip internal updation of document on setting Text property.
		skipUpdating = True
		Dim stream As Stream = New MemoryStream()
		' Saves the document's text into a Stream.
		Me.Save(stream, FormatType.Txt)
		stream.Position = 0
		' Reads the text from the stream.
		Using reader As New StreamReader(stream)
			Me.Text = reader.ReadToEnd()
		End Using
		skipUpdating = False
	End If
End Sub
#End Region

#Region "Implementation"
''' <summary>
''' Updates the document.
''' </summary>
''' <param name="text"></param>
Private Sub UpdateDocument(text As String)
	' If text property is set internally means, skip updating the document.
	If Not skipUpdating AndAlso Not String.IsNullOrEmpty(text) Then
		Dim stream As Stream = New MemoryStream()
		' Convert the text to byte array.
		Dim bytes As Byte() = Encoding.UTF8.GetBytes(text)
		' Writes the byte array to stream.
		stream.Write(bytes, 0, bytes.Length)
		stream.Position = 0
		'Load the stream.
		Load(stream, FormatType.Txt)
	End If
End Sub
''' <summary>
''' Disposes the instance.
''' </summary>
Public Shadows Sub Dispose()
	RemoveHandler this.ContentChanged, AddressOf RicTextBoxAdv_ContentChanged
	ClearValue(TextProperty)
	MyBase.Dispose()
End Sub
#End Region
End Class


{% endhighlight %}
{% endtabs %}

## Creating XAML View

The following code example demonstrates how to create XAML view with SfRichTextBoxAdv and UI properties bound to view model properties.
{% tabs %}
{% highlight xml %}
<Window x:Class="Sample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="clr-namespace:Sample">

    <Window.DataContext>
        <local:ViewModel />
    </Window.DataContext>
    
    <Border>
        <Grid>
            <Grid.RowDefinitions>
                <RowDefinition Height="Auto"/>
                <RowDefinition Height="*"/>
            </Grid.RowDefinitions>
            <StackPanel Orientation="Horizontal" Margin="4">
                <TextBlock Text="Animal :"/>
                <ComboBox IsTabStop="False" ItemsSource="{Binding Animals}" SelectedValue="{Binding Animal, Mode=TwoWay}"/>
            </StackPanel>
            <Grid Margin="10" Grid.Row="1">
                <Grid.RowDefinitions>
                    <RowDefinition Height="Auto"/>
                    <RowDefinition Height="*"/>
                </Grid.RowDefinitions>
                <TextBlock Text="Description" />
                <Border BorderThickness="1" BorderBrush="#A3A3A3">
                    <local:SfRichTextBoxAdvExtension Grid.Row="1" Text="{Binding Path=Text,Mode=TwoWay}" LayoutType="Continuous"/>
                </Border>
            </Grid>
        </Grid>
    </Border>
</Window>


{% endhighlight %}

{% endtabs %}

N> You can refer to our [WPF RichTextBox](https://www.syncfusion.com/wpf-controls/richtextbox) feature tour page for its groundbreaking feature representations.You can also explore our [WPF RichTextBox example](https://github.com/syncfusion/wpf-demos/tree/master/richtextbox) to knows how to render and configure the editing tools.