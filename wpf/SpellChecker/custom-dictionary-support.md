---
layout: post
title: Custom Dictionary in WPF SfSpellChecker | Syncfusion
description: This section expalins how to create and add Custom Dictionary Supports for WPF SfSpellChecker control.
platform: WPF
control: SfSpellChecker
documentation: ug
---

# Dictionaries for SpellCheck

You can use a default and custom dictionaries to spell check the document based on your need. You can also spell check for any culture and languages using various dictionaries.

## Default SpellCheck Dictionary

[SfSpellChecker](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker.html) provides predefined dictionary for `English` language and provides a suitable suggestion of the error words.

## SpellCheck dictionaries for any culture 

You can spell check any language(culture) by adding the respective culture to the [SfSpellChecker.Culture](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~Culture.html) property and add the dictionaries which contains the basic word file and grammar file to the [SfSpellChecker.Dictionaries](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~Dictionaries.html) collection.

The following dictionary types are used for spell-checking,

 * HunSpell
 * Ispell
 * OpenOffice

## SpellCheck using Ispell dictionary

If you want to spell check the given document quickly and get a suitable suggestions for the error words, use the `Spell` dictionary. It is much smaller and more effective to spell check.

`Ispell` dictionary contains two files as follows,

* Affix file with grammar rules- `*.aff`, 
* Basic Words file - `*.xlg` or `*.dic` file.

### Adding Ispell Dictionary

1. Add your `IspellDictionary`'s required culture `*.aff` and `*.dic` files and add them as `Resource` into the application.

![Adding Basic word and Grammar files as resource into the application](Dictionary_images/IspellAdding.png)

2. Create a `IspellDictionary` instance and add the basic word & grammar file path to the `IspellDictionary.DictionaryUri` & `IspellDictionary.GrammarUri` properties and add the culture to the `IspellDictionary.Culture` property.

3.Add the  `IspellDictionary` into the `SfSpellChecker.Dictionaries` collection

4. Setting the required culture to the `SfSpellChecker.Culture` property.

{% tabs %}
{% highlight C# %}

//Creating TextSpell Editor

public class TextSpellEditor : IEditorProperties {
    TextBox textbox;
    public TextSpellEditor(Control control) {
        ControlToSpellCheck = control;
    }
    public Control ControlToSpellCheck {
        get {
            return textbox;
        }
        set {
            textbox = value as TextBox;
        }
    }

    public string SelectedText {
        get {
            return textbox.SelectedText;
        }
        set {
            textbox.SelectedText = value;
        }
    }

    public string Text {
        get {
            return textbox.Text;
        }
        set {
            textbox.Text = value;
        }
    }

    public void Select(int selectionStart, int selectionLength) {
        textbox.Select(selectionStart, selectionLength);
    }

    public bool HasMoreTextToCheck() {
        return false;
    }

    public void Focus() {
        textbox.Focus();
    }

    public void UpdateTextField() {
        throw new NotImplementedException();
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Grid VerticalAlignment="Center">
    <StackPanel>
        <TextBox Text="gracsq por venizr por favor ven de nuevoq" 
                 Height="300"
                 Width="300" 
                 x:Name="txtbx"
                 TextWrapping="Wrap"                
                 VerticalContentAlignment="Top"/>
        <Button HorizontalAlignment="Center"
                Content="Spell Check" 
                Click="Button_Click" >
        </Button>
    </StackPanel>
</Grid>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

//MainWindow.cs
public partial class MainWindow : Window {
    TextSpellEditor SpellEditor;
    public IEditorProperties Editor {
        get;
        set;
    }

    public SfSpellChecker SpellChecker {
        get;
        set;
    }

    public MainWindow() {
        SpellChecker = new SfSpellChecker();
        InitializeComponent();
        SpellEditor = new TextSpellEditor(txtbx);
        Editor = SpellEditor;

        //Creating a culture instance
        CultureInfo culture = new CultureInfo("es-ES");

        SpellChecker = new SfSpellChecker();

        // Adding Ispell dictonaries in Dictionaries collection
        SpellChecker.Dictionaries = new DictionaryCollection();

        //Add Spanish culture Ispell dictionary
        SpellChecker.Dictionaries.Add(
            new IspellDictionary()
            {
                Culture = culture,
                GrammarUri = new Uri("/IspellCheck;component//Spanish/es-ES.aff", UriKind.Relative),
                DictionaryUri = new Uri("/IspellCheck;component//Spanish/es-ES.dic", UriKind.Relative)
            }
        );

        //Setting a Spanish culture for SpellChecker
        SpellChecker.Culture = culture;
        SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
    }
    
    //Call SpellCheck method to open SpellCheck on button click
    private void Button_Click(object sender, RoutedEventArgs e) {
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
    }
}

{% endhighlight %}
{% endtabs %}

N> You can add multiple `IspellDictionary` with various culture files into the `SfSpellChecker.Dictionaries` collection. Based on the `SfSpellChecker.Culture` respective `IspellDictionary` is used for spell check.

![SpellCheck using Ispell dictionary](Dictionary_images/Ispell.png)

 ## SpellCheck using OpenOffice dictionary

If you want to spell check the given document with high accuracy than `IspellDictionary`, use the `OpenOffice` dictionary. It provides a more suggestion words than the `IspellDictionary`. 

`OpenOffice` dictionary contains two files as follows,

* Affix file with grammar rules- `*.aff`, 
* Basic Words file - `*.dic` file.

N> `Ispell` and `OpenOffice` have different rules in the Affix files, you can't use the same Affix files for both dictionaries.

### Adding OpenOffice Dictionary

1. Add your `OpenOfficeDictionary`'s required culture `*.aff` and `*.dic` files and add them as `Resource` into the application.

![Adding Basic word and Grammar files as resource into the application](Dictionary_images/OpenOfficeAdding.png)

2. Create a `OpenOfficeDictionary` instance and add the basic word & grammar file path to the `OpenOfficeDictionary.DictionaryUri` & `OpenOfficeDictionary.GrammarUri` properties and add the culture to the `OpenOfficeDictionary.Culture` property.

3.Add the  `OpenOfficeDictionary` into the `SfSpellChecker.Dictionaries` collection

4. Setting the required culture to the `SfSpellChecker.Culture` property.

{% tabs %}
{% highlight C# %}

//Creating TextSpell Editor

public class TextSpellEditor : IEditorProperties {
    TextBox textbox;
    public TextSpellEditor(Control control) {
        ControlToSpellCheck = control;
    }
    public Control ControlToSpellCheck {
        get {
            return textbox;
        }
        set {
            textbox = value as TextBox;
        }
    }

    public string SelectedText {
        get {
            return textbox.SelectedText;
        }
        set {
            textbox.SelectedText = value;
        }
    }

    public string Text {
        get {
            return textbox.Text;
        }
        set {
            textbox.Text = value;
        }
    }

    public void Select(int selectionStart, int selectionLength) {
        textbox.Select(selectionStart, selectionLength);
    }

    public bool HasMoreTextToCheck() {
        return false;
    }

    public void Focus() {
        textbox.Focus();
    }

    public void UpdateTextField() {
        throw new NotImplementedException();
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Grid VerticalAlignment="Center">
    <StackPanel>
        <TextBox Text="gracsq por venizr por favor ven de nuevoq" 
             Height="300"
             Width="300" 
             x:Name="txtbx"
             TextWrapping="Wrap"                
             VerticalContentAlignment="Top"/>
        <Button HorizontalAlignment="Center"
                Content="Spell Check" 
                Click="Button_Click">
        </Button>
    </StackPanel>
</Grid>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

//MainWindow.cs
public partial class MainWindow : Window {
    TextSpellEditor SpellEditor;

    public IEditorProperties Editor {
        get;
        set;
    }

    public SfSpellChecker SpellChecker {
        get;
        set;
    }

    public MainWindow() {
        SpellChecker = new SfSpellChecker();
        InitializeComponent();
        SpellEditor = new TextSpellEditor(txtbx);
        Editor = SpellEditor;

        //Creating a Spanish culture instance
        CultureInfo culture = new CultureInfo("es-ES");

        SpellChecker = new SfSpellChecker();

        // Adding OpenOffice dictonaries in Dictionaries collection
        SpellChecker.Dictionaries = new DictionaryCollection();

        //Add Spanish culture OpenOffice dictionary
        SpellChecker.Dictionaries.Add(
            new OpenOfficeDictionary()
            {
                Culture = culture,
                GrammarUri = new Uri("/OpenOfficeSpellCheck;component//Spanish/es-ES.aff", UriKind.Relative),
                DictionaryUri = new Uri("/OpenOfficeSpellCheck;component//Spanish/es-ES.dic", UriKind.Relative)
            }
        );

        //Setting a French culture for SpellChecker
        SpellChecker.Culture = culture;
        SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
    }
    
    //Call SpellCheck method to open SpellCheck on button click
    private void Button_Click(object sender, RoutedEventArgs e) {
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
    }
}

{% endhighlight %}
{% endtabs %}

N> You can add multiple `OpenOfficeDictionary` with various culture files into the `SfSpellChecker.Dictionaries` collection. Based on the `SfSpellChecker.Culture` respective `OpenOfficeDictionary` is used for spell check.

![SpellCheck using OpenOffice dictionary](Dictionary_images/OpenOffice.png)

## SpellCheck using HunSpell dictionary

If you want to spell check the given document with high accuracy and more suitable suggestions for the error words than the `OpenOffice` dictionary, use the `HunSpell` dictionary. It is used for any language with rich morphology and complex word compounding and character encoding.

`Hunspell` dictionary contains two files as follows,

* Affix file with grammar rules- `*.aff`, 
* Basic Words file - `*.dic` file.

### Adding HunSpell Dictionary

1. Add your `HunspellDictionary`'s required culture `*.aff` and `*.dic` files and add them as `Resource` into the application.

![Adding Basic word and Grammar files as resource into the application](Dictionary_images/HunspellAdding.png)

2. Create a `HunspellDictionary` instance and add the basic word & grammar file path to the `HunspellDictionary.DictionaryUri` & `HunspellDictionary.GrammarUri` properties and add the culture to the `HunspellDictionary.Culture` property.

3.Add the  `HunspellDictionary` into the `SfSpellChecker.Dictionaries` collection

4. Setting the required culture to the `SfSpellChecker.Culture` property.

{% tabs %}
{% highlight C# %}

//Creating TextSpell Editor

public class TextSpellEditor : IEditorProperties {
    TextBox textbox;
    public TextSpellEditor(Control control) {
        ControlToSpellCheck = control;
    }
    public Control ControlToSpellCheck {
        get {
            return textbox;
        }
        set {
            textbox = value as TextBox;
        }
    }

    public string SelectedText {
        get {
            return textbox.SelectedText;
        }
        set {
            textbox.SelectedText = value;
        }
    }

    public string Text {
        get {
            return textbox.Text;
        }
        set {
            textbox.Text = value;
        }
    }

    public void Select(int selectionStart, int selectionLength) {
        textbox.Select(selectionStart, selectionLength);
    }

    public bool HasMoreTextToCheck() {
        return false;
    }

    public void Focus() {
        textbox.Focus();
    }

    public void UpdateTextField() {
        throw new NotImplementedException();
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Grid VerticalAlignment="Center">
    <StackPanel>
        <TextBox Text="Nous sommevs heureusre de vous avohir ici" 
                 Height="300"
                 Width="300" 
                 x:Name="txtbx"
                 TextWrapping="Wrap"                
                 VerticalContentAlignment="Top"/>
        <Button HorizontalAlignment="Center"
                Content="Spell Check"
                Click="Button_Click">
        </Button>
    </StackPanel>
</Grid>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

public partial class MainWindow : Window {
    TextSpellEditor SpellEditor;

    public IEditorProperties Editor {
        get;
        set;
    }

    public SfSpellChecker SpellChecker {
        get;
        set;
    }
    public MainWindow() {
        SpellChecker = new SfSpellChecker();
        InitializeComponent();
        SpellEditor = new TextSpellEditor(txtbx);
        Editor = SpellEditor;

        //Creating a culture instance
        CultureInfo culture = new CultureInfo("fr-FR");

        // Adding HunSpell dictonaries in Dictionaries collection
        SpellChecker.Dictionaries = new DictionaryCollection();

        //Add French culture HunSpell dictionary
        SpellChecker.Dictionaries.Add(
            new HunspellDictionary()
            {
                Culture = culture,
                GrammarUri = new Uri("/HunSpellCheck;component//French/fr-FR.aff", UriKind.Relative),
                DictionaryUri = new Uri("/HunSpellCheck;component//French/fr-FR.dic", UriKind.Relative)
            }
        );

        //Setting a French culture for SpellChecker
        SpellChecker.Culture = culture;
        SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
    }

    //Call SpellCheck method to open SpellCheck on button click
    private void Button_Click(object sender, RoutedEventArgs e) {
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
    }
}

{% endhighlight %}
{% endtabs %}

N> You can add multiple `HunSpellDictionary` with various culture files into the `SfSpellChecker.Dictionaries` collection. Based on the `SfSpellChecker.Culture` respective `HunSpellDictionary` is used for spell check.

![SpellCheck using HunSpell dictionary](Dictionary_images/HunSpell.png)

## SpellCheck using Custom Dictionary

If you want to skip or make the error or custom word as correct word, add that word into the custom dictionary text file. You can add that word on before perform spell check by directly adding that words into the custom dictionary text file and also can add the error word into the custom dictionary text file at runtime by clicking the `Add to Dictionary` button. Then, while performing next spell check, Custom dictionary text file contained words are considered as a correct words.  

### Adding Custom Dictionary

1. Create a custom dictionary text file as `Resource` into the application

![Adding custom word files as resource into the application](Dictionary_images/CustomDictionaryAdding.png)

2. Create a `CustomDictionary` instance and add the custom word file path to the `CustomDictionary.DictionaryUri` property and add the culture to the `CustomDictionary.Culture` property.

3.Add the  `CustomDictionary` into the `SfSpellChecker.Dictionaries` collection

4. Setting the required culture to the `SfSpellChecker.Culture` property.

{% tabs %}
{% highlight C# %}

//Creating TextSpell Editor

public class TextSpellEditor : IEditorProperties {
    TextBox textbox;
    public TextSpellEditor(Control control) {
        ControlToSpellCheck = control;
    }
    public Control ControlToSpellCheck {
        get {
            return textbox;
        }
        set {
            textbox = value as TextBox;
        }
    }

    public string SelectedText {
        get {
            return textbox.SelectedText;
        }
        set {
            textbox.SelectedText = value;
        }
    }

    public string Text {
        get {
            return textbox.Text;
        }
        set {
            textbox.Text = value;
        }
    }

    public void Select(int selectionStart, int selectionLength) {
        textbox.Select(selectionStart, selectionLength);
    }

    public bool HasMoreTextToCheck() {
        return false;
    }

    public void Focus() {
        textbox.Focus();
    }

    public void UpdateTextField() {
        throw new NotImplementedException();
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Grid VerticalAlignment="Center">
    <StackPanel>
        <TextBox Text="Ribbn illustrats the Microsoft illustrats Offce 2007 UI. Our prduct exposes most of the featres of the new UI and eeps intact winhth the Slverlight architecture. Configuring and designing the layout is very easy through XAML code. Ribbon tabs and Ribbon bars are the main client area in Ribbon. Ribbon tabs will allow your end users to navigate and find the appropriate tools for the task at hand. The Ribbon bars will contain the Ribbon tools."
                 Height="300"
                 Width="300" 
                 x:Name="txtbx"
                 TextWrapping="Wrap"                
             VerticalContentAlignment="Top"/>
        <Button HorizontalAlignment="Center"
                Content="Spell Check" 
                Click="Button_Click">
        </Button>
    </StackPanel>
</Grid>

{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight C# %}

//MainWindow.cs
public partial class MainWindow : Window {
    
    TextSpellEditor SpellEditor;

    public IEditorProperties Editor {
        get;
        set;
    }

    public SfSpellChecker SpellChecker {
        get;
        set;
    }
    public MainWindow() {
        SpellChecker = new SfSpellChecker();
        InitializeComponent();
        SpellEditor = new TextSpellEditor(txtbx);
        Editor = SpellEditor;

        //Creating a culture instance
        CultureInfo culture = new CultureInfo("en-US");

        // Get the current PROJECT directory
        string projectDirectory = Directory.GetParent(Environment.CurrentDirectory).Parent.FullName;

        //Add US culture Custom dictionary
        SpellChecker.Dictionaries.Add(
            new CustomDictionary()
            {
                Culture = culture,
                DictionaryUri = new Uri(projectDirectory + @"\English\Custom_en-US.txt", UriKind.Absolute)
            }
        );

        //Setting a US culture for SpellChecker
        SpellChecker.Culture = culture;
        SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
    }

    //Call SpellCheck method to open SpellCheck on button click
    private void Button_Click(object sender, RoutedEventArgs e) {
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
    }
}

{% endhighlight %}
{% endtabs %}

N> You can add multiple `CustomDictionary` with various culture files into the `SfSpellChecker.Dictionaries` collection. Based on the `SfSpellChecker.Culture` respective `CustomDictionary` is used for spell check.

![SpellCheck using Custom dictionary](Dictionary_images/CustomDictionary.png)

N> View [Sample](https://github.com/SyncfusionExamples/WPF-SpellChecker-examples/tree/master/Samples/CustomSpellCheck) in GitHub
