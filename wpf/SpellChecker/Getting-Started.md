---
layout: post
title: Getting Started with wpf SfSpellChecker control | Syncfusion
description: This section describes about how to create a WPF SfSpellChecker and how to spell check the text using it.
platform: WPF
control: SfSpellChecker
documentation: ug
--- 

# Getting Started with WPF SfSpellChecker

This section explains how to create a WPF [SfSpellChecker](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker.html) and spell check the text.

## Control Structure

![SpeckChecker created for the Text editor](gettingstarted-images/Control_Structure.png)

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfspellchecker) section to get the list of assemblies or NuGet package that needs to be added as reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: 

[How to install nuget packages](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages)

## Adding WPF SfSpellChecker to an application

Spell checking operation can be done on text editor controls through `SfSpellChecker` in WPF application by implementing `IEditorProperties` interface. 

You can add the `SfSpellChecker` and text editor to an application by the following steps,

1. Create a WPF project in Visual Studio and include following assemblies.

* Syncfusion.SpellChecker.Base
* Syncfusion.SfSpellChecker.WPF

2. Create a `TextSpellEditor` by implementing the [IEditorProperties](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.IEditorProperties.html) interface members.

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

3. Create instance of `Button` and `TextBox` to input control for SpellCheck.

{% tabs %}
{% highlight XAML %}

<Grid VerticalAlignment="Center">
    <StackPanel>
        <TextBox Text="Natusre is an importsant and integral part of mankind. 
                       It is one of the greattest blessings for human lifve.
                       Howeverq, nowadays humans fail to recognize it as one.
                       Nature has been an inspiration for numerous poets,
                       writeqrs, artists and more of yesteryears."
                 Name="textbox"
                 TextWrapping="Wrap"                
                 VerticalContentAlignment="Top"/>
        <Button HorizontalAlignment="Center"
                Content="Spell Check"
                Click="SpellCheck_ButtonClick">
        </Button>
    </StackPanel>
</Grid>

{% endhighlight %}
{% endtabs %}

4. Create a instance for `SfSpellChecker` and `TextSpellEditor`, then load the spell checker on button click by calling the [PerformSpellCheckUsingDialog](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~PerformSpellCheckUsingDialog.html) method.

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
    }
    
    //Call SpellCheck method to open SpellCheck on button click
    private void SpellCheck_ButtonClick(object sender, RoutedEventArgs e) {
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
    }
}

{% endhighlight %}
{% endtabs %}

![SpeckChecker created for the Text editor](gettingstarted-images/Getting_Started.png)

N> View [Sample](https://github.com/SyncfusionExamples/WPF-SpellChecker-examples/tree/master/Samples/SfSpellChecker) in GitHub

## Fix spelling mistakes using spell check dialog

1. You can open a `SfSpellChecker` by clicking `Spell Check` button and then `SpellChecker` opened as pop-up with `TextSpellEditor`. 

2. The error words are highlight with `Red` foreground. 

3. You can replace error words with correct words by double click the suitable word listed in the suggestion listbox or select the suggestion word from the listbox and then press the `Change` button.

![SpeckCheck using SfSpellChecker](gettingstarted-images/SpellCheck_Button.gif)

N> View [Sample](https://github.com/SyncfusionExamples/WPF-SpellChecker-examples/tree/master/Samples/SfSpellChecker) in GitHub

## Fix spelling mistakes using context menu

You can simply correct the spell error words by choosing the correct option from listed suggestions from the ContextMenu. You can enable context menu suggestion by using the [PerformSpellCheckUsingContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~PerformSpellCheckUsingContextMenu.html) method and can get the suggestion words by right click on the error word. The Error words are differentiated by red underlining.

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

        //Enable Contextmenu to spellcheck
        SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
    }
    
    //Call SpellCheck method to open SpellCheck on button click
    private void Button_Click(object sender, RoutedEventArgs e) {
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
    }
}

{% endhighlight %}
{% endtabs %}

![SpeckCheck using contextmenu](gettingstarted-images/contextmenu.gif)

N> View [Sample](https://github.com/SyncfusionExamples/WPF-SpellChecker-examples/tree/master/Samples/SfSpellChecker) in GitHub

## Get suggestions for misspelled word

You can get the suggestion list by passing the error word in the below methods.

* [GetSuggestions](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~GetSuggestions.html) - To get a list of suggestion words for an error word
* [GetPhoneticWords](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~GetPhoneticWords.html) - To get a list of phonetic words for an error word
* [GetAnagrams](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~GetAnagrams(String).html) - To get a list of anagram words for an error word

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
    }
    
    //Call SpellCheck method to open SpellCheck on button click
    private void Button_Click(object sender, RoutedEventArgs e) {
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
    }
}

{% endhighlight %}
{% endtabs %}

## Ignore SpellCheck for particular types of text

If you want to ignore the error words such a format like email id's and link addresses, HTML tags, combination of words and numbers, combination of upper and lower case words, use the respective property value as `true` from the following table,

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td><td>
Example<br/><br/></td>
</tr>
<tr>
<td>
IgnoreEmailAddress<br/><br/></td><td>
Specifies whether or not to ignore email address during Spell Check. 


The Default value is False.<br/><br/></td><td>
Ex: 

john@abc.com<br/><br/></td></tr>
<tr>
<td>
IgnoreHtmlTags<br/><br/></td><td>
Specifies whether or not to ignore HTML tags during Spell Check. 

The Default value is False.<br/><br/></td><td>
Ex: 

< html></ html> <br/><br/></td></tr>
<tr>
<td>
IgnoreUrl<br/><br/></td><td>
Specifies whether or not to ignore Internet address during Spell Check.

The Default value is False.<br/><br/></td><td>
Ex:

 https://help.syncfusion.com/<br/><br/></td></tr>
<tr>
<td>
IgnoreMixedCaseWords<br/><br/></td><td>
Specifies whether or not to ignore mixed case words during Spell Check.

The Default value is False.<br/><br/></td><td>
Ex:

AbCDeFH <br/><br/></td></tr>
<tr>
<td>
IgnoreUpperCaseWords<br/><br/></td><td>
Specifies whether or not to ignore uppercase words during Spell Check.

The Default value is False.<br/><br/></td><td>
Ex:

ABCDE <br/><br/></td></tr>
<tr>
<td>
IgnoreAlphaNumericWords<br/><br/></td><td>
Specifies whether or not to Spell Check numbers or words with numbers during Spell Check.

The Default value is False.<br/><br/></td><td>
Ex:

A*&%#9

ACe&981 <br/><br/></td></tr>
</table>

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
        SpellChecker.IgnoreUrl = true;
        SpellChecker.IgnoreUpperCaseWords = true;
        SpellChecker.IgnoreAlphaNumericWords = true;
        SpellChecker.IgnoreEmailAddress = true;
        SpellChecker.IgnoreMixedCaseWords = true;
        SpellChecker.IgnoreHtmlTags = true;
    }
    
    //Call SpellCheck method to open SpellCheck on button click
    private void Button_Click(object sender, RoutedEventArgs e) {
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
    }
}

{% endhighlight %}
{% endtabs %}

## SpellCheck for any language(culture) 

You can spell check any language(culture) by adding the respective culture to the [SfSpellChecker.Culture](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~Culture.html) property and add the dictionaries which contains the basic word file and grammar file to the [SfSpellChecker.Dictionaries](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~Dictionaries.html) collection.

The following dictionary types are used for spell-checking,

 * Hunspell
 * Ispell
 * OpenOffice

 N> Refer the [Dictionary for any culture]
(https://help.syncfusion.com/wpf/spellchecker/custom-dictionary-support#spellCheck-dictionaries-for-any-culture) page to know more about how to add and use the Dictionary for any culture to an application.

## Add custom words to dictionary

If you want to add words that is not available in dictionary, you can add it using `CustomDictionary`. This dictionary does not has a grammar file, it accepts only dictionary file that contains a list of words. Users can also add words to this custom dictionary by clicking `Add to Dictionary` button available in dialog or context menu.

N> Refer the [Custom Dictionary](https://help.syncfusion.com/wpf/spellchecker/custom-dictionary-support#adding-custom-dictionary) page to know more about how to add and use the custom dictionary to an application.

## Event to notify when spell check is completed

By default, when the spell check is completed, it will be notified by using the message box that showing the `Spell check is completed` message. If you want to restrict that message box, you can handle the [SpellCheckCompleted](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~SpellCheckCompleted_EV.html) event and set the [SpellCheckCompletedEventArgs.ShowMessageBox](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SpellCheckCompletedEventArgs~ShowMessageBox.html) to `false`.

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
        SpellChecker.SpellCheckCompleted += SpellChecker_SpellCheckCompleted;
    }

    //Call SpellCheck method to open SpellCheck on button click
    private void Button_Click(object sender, RoutedEventArgs e) {
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
    }

    private void SpellChecker_SpellCheckCompleted(object sender, EventArgs e) {
        //Restrict the message box showing
        (e as SpellCheckCompletedEventArgs).ShowMessageBox = false;
    }
}

{% endhighlight %}
{% endtabs %}

![SpellChecker restrict the speck check completed notification message box](gettingstarted-images/SpellCheckCompletedEventArgs_ShowMessageBox.png)

N> View [Sample](https://github.com/SyncfusionExamples/WPF-SpellChecker-examples/tree/master/Samples/SfSpellChecker) in GitHub


