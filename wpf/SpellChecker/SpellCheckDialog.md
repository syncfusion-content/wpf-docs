---
layout: post
title: SpellCheckDialog | SpellChecker | wpf | Syncfusion
description: spellcheckdialog
platform: wpf
control: SpellChecker
documentation: ug
---

# SpellCheckDialog

Spell Checker contains in-built dialog for checking spellings for any input control. SpellChecker will not directly checks spelling for the control. You need to create a wrapper class for that control by implementing the interface ISpellEditor and you need to define all the members given in the interface. Using this interface the SpellChecker will interact with any control.

### Methods

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
SpellCheckForEditor</td><td>
SpellCheckForEditor(ISpellEditor editor)</td><td>
If you use this method for checking spellings, the SpellChecker will launch a SpellCheckDialog.Using this dialog you can ignore, replace  and add the selected word to the dictionary.</td></tr>
</table>


### Events

<table>
<tr>
<th>
Event</th><th>
Parameters</th><th>
Description</th></tr>
<tr>
<td>
SpellCheckCompleted</td><td>
 Nil</td><td>
This event will be triggered when the spell checking is completed for the input text using SpellCheckDialog</td></tr>
</table>


## Spell Checking Using ISpellEditor 

In the below code snippet, a wrapper class is created for TextBox by implementing ISpellEditor interface.

{%highlight c# %}

public class TextBoxSpellEditor : ISpellEditor

{

	private TextBox textBox;

	public TextBoxSpellEditor(Control control)

	{

		ControlToCheck = control;

	}

	public Control ControlToCheck

	{

		get

		{

			return textBox;

		}

		set

		{

			textBox = value as TextBox;

		}

	}

	public string SelectedText

	{

		get

		{

			return textBox.SelectedText;

		}

		set

		{

			textBox.SelectedText = value;

		}

	}

	public string Text

	{

		get

		{

			return textBox.Text;

		}

		set

		{

			textBox.Text = value;

		}

	}

	public void Select(int selectionStart, int selectionLength)

	{

		textBox.Select(selectionStart, selectionLength);

	}

	public bool HasMoreTextToCheck()

	{

		return false;

	}
	
	public void Focus()

	{

		textBox.Focus();

	}

	public void UpdateTextField()

	{

	}

}

{% endhighlight %}

After creating the wrapper class, you need to pass the instance of the ISpellEditor to SpellCheckForEditor method as given in the following code snippet:

{% highlight c# %}

SpellChecker spellCheck = new SpellChecker();

TextBoxSpellEditor spellEditor = new TextBoxSpellEditor(txtbx);

spellCheck.SpellCheckForEditor(spellEditor);

{% endhighlight %}

#### Sample Link

To access the sample link:

1. Open the Syncfusion Dashboard.
2. Select User Interface.
3. Click the WPF drop-down list and select Explore Samples.
4. Navigate to Tools -> SpellChecker -> SpellCheckerDemo.