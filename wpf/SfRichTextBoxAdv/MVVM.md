---
title: MVVM
description: mvvm
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: mvvm
---
# MVVM

The SfRichTextBoxAdv control can be used with Model-View-View Model (MVVM) pattern. This section will demonstrate how to use the SfRichTextBoxAdv control with MVVM pattern.
## Creating a View Model

The following code example demonstrates how to implement a view model class that contains properties to preserve the description about some of the animals and the animal that is selected for discussion. Whenever the animal chosen for discussion is changed, previously chosen animal description is updated to the data base and newly chosen animal description is updated to the text property.
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
        animals.Add("Lion", "The lion (Panthera leo) is one of the five big cats in the genus Panthera and a member of the family Felidae.");
        animals.Add("Panda", "The giant panda, also known as panda bear or simply panda, is a bear native to south central China. It is easily recognized by the large, distinctive black patches around its eyes, over the ears, and across its round body.");
        animals.Add("Beer", "Bears are mammals of the family Ursidae. Bears are classified as caniforms, or doglike carnivorans, with the pinnipeds being their closest living relatives.");
        animals.Add("Deer", "Deer are the ruminant mammals forming the family Cervidae. Species in the family include the white-tailed deer, mule deer, elk, moose, red deer, reindeer, fallow deer, roe deer, pudú and chital.");

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
