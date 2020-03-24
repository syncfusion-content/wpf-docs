---
layout: post
title: Spell-Checking-Options | SfSpellChecker | wpf | Syncfusion
description: This section describes about various Spell Checking Options available in SpellChecker control and how it can be assigned to the control.
platform: WPF
control: SfSpellChecker
documentation: ug
---

# Spell Check

The Spell Checking engine can also be customized to ignore certain text or words from being spell checked. By setting the respective properties, these words will be overlooked and will not indicate them as misspelled words. This option will be effective when there are a number of email id’s and addresses, HTML tags, combination of words and numbers, combination of upper and lower case words that are used frequently in the document.

## Ignore Spell Check

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
IgnoreEmailAddress<br/><br/></td><td>
Specifies whether or not to ignore email address during Spell Check. Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreHtmlTags<br/><br/></td><td>
Specifies whether or not to ignore HTML tags during Spell Check. Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreUrl<br/><br/></td><td>
Specifies whether or not to ignore Internet address during Spell Check. Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreMixedCaseWords<br/><br/></td><td>
Specifies whether or not to ignore mixed case words during Spell Check.  Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreUpperCaseWords<br/><br/></td><td>
Specifies whether or not to ignore uppercase words during Spell Check. Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreAlphaNumericWords<br/><br/></td><td>
Specifies whether or not to Spell Check numbers or words with numbers during Spell Check. Default value is False.<br/><br/></td></tr>
</table>


## Setting Spell Check Options

Create a spell checker instance and set the spell checking options as given below:

{% tabs %}

{% highlight C# %}

        TextSpellEditor SpellEditor;

        public MainWindow()
        {
            SpellChecker = new SfSpellChecker();
            InitializeComponent();
            SpellEditor = new TextSpellEditor(txtbx);
            Editor = SpellEditor;
            SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
            SpellChecker.IgnoreUrl = true;
            SpellChecker.IgnoreUpperCaseWords = true;
            SpellChecker.IgnoreAlphaNumericWords = true;
            SpellChecker.IgnoreEmailAddress = true;
            SpellChecker.IgnoreMixedCaseWords = true;
            SpellChecker.IgnoreHtmlTags = true;
        }

        public IEditorProperties Editor
        {
            get;
            set;
        }

        public SfSpellChecker SpellChecker
        {
            get;
            set;
        }

{% endhighlight %}

{% endtabs %}


## Getting Suggestions for Error Word

`SfSpellChecker` provides support to get suggestion list by passing the error word in the below methods.

* GetSuggestions
* GetPhoneticWords
* GetAnagrams

{% tabs %}
{% highlight C# %}

        TextSpellEditor SpellEditor;

        public MainWindow()
        {
            SpellChecker = new SfSpellChecker();
            InitializeComponent();
            SpellEditor = new TextSpellEditor(txtbx);
            Editor = SpellEditor;
            SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
        }

        public IEditorProperties Editor
        {
            get;
            set;
        }

        public SfSpellChecker SpellChecker
        {
            get;
            set;
        }

SpellChecker.GetSuggestions("offce");
SpellChecker.GetPhoneticWords("offce");
SpellChecker.GetAnagrams("offce");

{% endhighlight %}
{% endtabs %}

## SpellCheckCompleted Notification

By default, when the spell check is completed, it will be notified by using the message box that showing the `Spell check is completed` message. If you want to restrict that message box, you can handle the [SpellCheckCompleted](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SfSpellChecker~SpellCheckCompleted_EV.html) event and set the [SpellCheckCompletedEventArgs.ShowMessageBox](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSpellChecker.WPF~Syncfusion.Windows.Controls.SpellCheckCompletedEventArgs~ShowMessageBox.html) to `false`.

1. Create an instance of `SfSpellChecker` and invoke the `SpellCheckCompleted` event

{% tabs %}
{% highlight C# %}

public class ViewModel : NotificationObject {
    public SfSpellChecker SpellChecker { get; set; }

    public bool showMessageBox = true;
    public bool ShowMessageBox {
        get {
            return showMessageBox;
        }
        set {
            showMessageBox = value;
            RaisePropertyChanged("ShowMessageBox");
        }
    }
    public IEditorProperties Editor { get; set; }

    private ICommand buttonclick;
    public ICommand Buttonclick {
        get {
            return buttonclick;
        }
        set {
            buttonclick = value;
            RaisePropertyChanged("Buttonclick");
        }
    }

    public ViewModel() {
        SpellChecker = new SfSpellChecker();           
        Buttonclick = new DelegateCommand(LoadItems, CanLoad);
    }
    private bool CanLoad(object arg) {
        return true;
    }
    private void LoadItems(object obj) {
        Editor = new TextSpellEditor(obj as TextBox);
        SpellChecker.SpellCheckCompleted += SpellChecker_SpellCheckCompleted;
        SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
        SpellChecker.PerformSpellCheckUsingDialog(Editor);
        
    }

    private void SpellChecker_SpellCheckCompleted(object sender, EventArgs e) {
        //Restrict the message box showing
        (e as SpellCheckCompletedEventArgs).ShowMessageBox = false;
    }
}

{% endhighlight %}
{% endtabs %}

2. Inherit `IEditorProperties` interface of `SfSpellChecker` and Initialize all the methods and properties in interface.

{% tabs %}
{% highlight C# %}

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

3. Create instance of `Button` and `TextBox` to input control for `SfSpellCheck`.

{% tabs %}
{% highlight xaml %}

<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>

 <TextBox x:Name="txtbx" FontSize="14" TextWrapping="Wrap" VerticalContentAlignment="Top"   VerticalAlignment="Stretch" >
     <TextBox.Text>
         Natue, in the broaest sense, is the natural, physical, or material world or universe. "Nature" can refer to the phenomena of the physical world, and also to life in general. The study of nature is a large, if not the only, part of science. Although humans are part of nature, human activity is often understood as a separate category from other natural phenomena.    
     </TextBox.Text>
 </TextBox>
<Button x:Name="button" FontWeight="Normal" HorizontalAlignment="Left" VerticalAlignment="Center"  Content="Spell Check" Command="{Binding Buttonclick}" CommandParameter="{Binding ElementName=txtbx}"/>
           
{% endhighlight %}
{% endtabs %}

![SpellChecker restrict the speck check completed notification message box](gettingstarted-images/SpellCheckCompletedEventArgs_ShowMessageBox.png)

Click [here](https://github.com/SyncfusionExamples/WPF-SpellChecker-examples/tree/master/SfSpellChecker) to downlaod the sample that showcases the speck check completed notification restriction.
