---
title: Undo Redo in WPF RichTextBox control | Syncfusion
description: Learn here all about Undo Redo support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: undo-redo
---
# Undo Redo in WPF RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv provides history preservation support, which means each editing operation performed against its document content will be preserved in history. You can easily undo any editing action with ease. The undone actions will also be preserved in a separate stack enabling you to redo the action again.

N> Currently, the number of actions that can be preserved in both undo and redo stacks is limited to 500.

## UI Command to perform undo/redo operations

The following code example demonstrates how to bind commands for performing undo and redo operations.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the UndoCommand -->
<Button Content="Undo" Command="RichTextBoxAdv:SfRichTextBoxAdv.UndoCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the RedoCommand -->
<Button Content="Redo" Command="RichTextBoxAdv:SfRichTextBoxAdv.RedoCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}

N> In order to perform undo/redo, the standard keyboard shortcuts such as CTRL + Z, CTRL + Y can also be used.

## Enable/Disable Undo Redo

### Disable Undo for all the editing actions

In SfRichTextBoxAdv, the Undo functionality is enabled by default. You can disable it by using the `IsUndoEnabled` property of the `EditorSettings` class.

The following code example demonstrates how to disable the Undo functionality in `SfRichTextBoxAdv`.
{% tabs %}
{% highlight xaml %}
<Syncfusion:SfRichTextBoxAdv x:Name="richTextBoxAdv">
	<Syncfusion:SfRichTextBoxAdv.EditorSettings>
		<Syncfusion:EditorSettings IsUndoEnabled="False"/>
	</Syncfusion:SfRichTextBoxAdv.EditorSettings>
</Syncfusion:SfRichTextBoxAdv>


{% endhighlight %}
{% highlight c# %}
// Defines the SfRichTextBoxAdv control with undo operation disabled.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
richTextBoxAdv.EditorSettings.IsUndoEnabled = false;


{% endhighlight %}
{% highlight VB %}
' Defines the SfRichTextBoxAdv control with undo operation disabled.
Dim richTextBoxAdv As New SfRichTextBoxAdv()
richTextBoxAdv.EditorSettings.IsUndoEnabled = false


{% endhighlight %}

{% endtabs %}

N> This API is supported starting from release version v18.1.0.X.

### Disable Undo for style modification actions

In SfRichTextBoxAdv, the Undo functionality is enabled by default for all the editing operations. If you want to disable the Undo functionality for modifying an existing style alone. You can disable it by using the `CanUndoStyle` property of the `EditorSettings` class.

The following code example demonstrates how to disable the Undo support for modifying an existing style in `SfRichTextBoxAdv`.
{% tabs %}
{% highlight xaml %}
<Syncfusion:SfRichTextBoxAdv x:Name="richTextBoxAdv">
	<Syncfusion:SfRichTextBoxAdv.EditorSettings>
		<Syncfusion:EditorSettings CanUndoStyle="False"/>
	</Syncfusion:SfRichTextBoxAdv.EditorSettings>
</Syncfusion:SfRichTextBoxAdv>


{% endhighlight %}
{% highlight c# %}
// Defines the SfRichTextBoxAdv control with document style undo operation disabled.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
richTextBoxAdv.EditorSettings.CanUndoStyle = false;


{% endhighlight %}
{% highlight VB %}
' Defines the SfRichTextBoxAdv control with document style undo operation disabled.
Dim richTextBoxAdv As New SfRichTextBoxAdv()
richTextBoxAdv.EditorSettings.CanUndoStyle = false


{% endhighlight %}

{% endtabs %}

N> This API is supported starting from release version v18.1.0.X.
