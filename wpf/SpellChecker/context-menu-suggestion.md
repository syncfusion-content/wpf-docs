---
layout: post
title: Context Menu Suggestion
description: Context Menu Suggestion support to text controls in WPF
platform: WPF
control: SfSpellChecker
documentation: ug
--- 

# Context Menu Suggestion

`SfSpellChecker` offers Microsoft Office application like context menu suggestions and helps to correct spell errors by choosing correct option from listed suggestions.

The following steps helps to add context menu suggestion in the TextBox control.

1 . Create a WPF project in Visual Studio.

2 . Create a class which inherits `IEditorProperties` interface of `SfSpellChecker` and Initialize all the methods and properties.

{% tabs %}

{% highlight C# %}

public class TextSpellEditor:IEditorProperties

{

TextBox textbox;

public TextSpellEditor(Control control)

{

ControlToSpellCheck = control;

}

public Control ControlToSpellCheck

{

get

{

return textbox;

}

set

{

textbox = value as TextBox;

}

}

public string SelectedText

{

get

{

return textbox.SelectedText;

}

set

{

textbox.SelectedText = value;

}

}

public string Text

{

get

{

return textbox.Text;

}

set

{

textbox.Text = value;

}

}

public void Select(int selectionStart, int selectionLength)

{

textbox.Select(selectionStart, selectionLength);

}

public bool HasMoreTextToCheck()

{

return false;

}

public void Focus()

{

textbox.Focus();

}

public void UpdateTextField()

{

throw new NotImplementedException();

}

}

{% endhighlight %}

{% endtabs %}


3 . Initiate `PerformSpellCheckUsingContextMenu` method by passing `IEditorProperties` interface argument.

{% tabs %}

{% highlight C# %}

TextSpellEditor TextEditor = new TextSpellEditor(txtbx);

SpellEditor = TextEditor;  

SpellChecker.PerformSpellCheckUsingContextMenu(SpellEditor);

{% endhighlight %}

{% endtabs %}

![](contextmenusuggestion-images/context-menu-suggestion.jpeg)


