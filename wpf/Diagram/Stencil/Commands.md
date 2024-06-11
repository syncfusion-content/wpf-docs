---
layout: post
title: Commands Support for Stencil in WPF Diagram control | Syncfusion
description: Learn here all about keyboard commands support for Stencil in Syncfusion WPF Diagram (SfDiagram) control ports.
platform: wpf
control: SfDiagram
documentation: ug
---

# Command Manager for Stencil in WPF Diagram (SfDiagram)

The Stencil in the WPF Diagram (SfDiagram) library now supports a variety of keyboard commands. These enhancements allow users to navigate through symbols, select multiple symbols, and perform clipboard operations efficiently, all without using a mouse. The `CommandManager` for the Stencil control enhances this functionality by enabling users to map keyboard gestures to specific Stencil commands, add new gesture commands, and remove existing ones. This integration significantly improves the flexibility and usability of the Stencil.

## Built-in Commands and Key Gestures

Stencil's `CommandManager` provides a range of built-in commands that can be executed using specific key gestures. Below is a list of common commands and their corresponding key gestures.

| Command | Key | Key Modifiers |
|---|---|---|
| Cut | X| Control |
| Copy | C | Control |
| Paste | V | Control |
| SelectAll | A	| Control |
| UnSelect | Escape |  |
| Delete | Delete |	|
| MoveLeft | Left | |	
| MoveRight | Right | |
| MoveUp | Up |	|
| MoveDown | Down |	|
| MoveToFirstInRow | Home |	|
| MoveToLastInRow | End | |
| MoveToFirstInColumn | Page Up | |
| MoveToLastInColumn | Page Down | |

## Cut Command

The `Cut` command removes the selected symbol from the stencil and stores it on the clipboard. Cut command can be executed by the keyboard shortcut CTRL + X.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Cut" Click="CutBtn_Click" ToolTip="Ctrl + X"></Button>

{% endhighlight %}

{% highlight C# %}

    private void CutBtn_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.Cut.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}

## Copy Command

The `Copy` command copies the selected symbol from the stencil and stores it on the clipboard. Copy command can be executed by the keyboard shortcut CTRL + C.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Copy" Click="CopyBtn_Click" ToolTip="Ctrl + C"></Button>

{% endhighlight %}

{% highlight C# %}

    private void CopyBtn_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.Copy.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}

## Paste Command

The `Paste` command inserts the symbol into the symbol group that was previously stored in the clipboard. Paste command can be executed by the keyboard shortcut CTRL + V.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Paste" Click="PasteBtn_Click" ToolTip="Ctrl + V"></Button>

{% endhighlight %}

{% highlight C# %}

    private void PasteBtn_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.Paste.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}


## Delete Command

The `Delete` command removes the selected symbol from the symbol group. Delete command can be executed by pressing the Delete key.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="Delete" Click="DeleteBtn_Click" ToolTip="Delete"></Button>

{% endhighlight %}

{% highlight C# %}

    private void DeleteBtn_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.Delete.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}

![Gif for Stencil Clipboard Commands](Stencil_Images/StencilClipboardCommands.gif)

## SelectAll Command

The `SelectAll` command selects all symbols in the symbol group. SelectAll command can be executed by the keyboard shortcut CTRL + A.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="SelectAll" Click="SelectAllBtn_Click" ToolTip="Ctrl + A"></Button>

{% endhighlight %}

{% highlight C# %}

    private void SelectAllBtn_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.SelectAll.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}


## UnSelect Command

The `UnSelect` command deselects any currently selected symbol in the stencil. UnSelect command can be executed by pressing the Escape key.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="UnSelect" Click="UnSelect_Click" ToolTip="Esc"></Button>

{% endhighlight %}

{% highlight C# %}

    private void UnSelect_Click(object sender, RoutedEventArgs e)
    {
    if (Stencil != null)
    {
        Stencil.Commands.UnSelect.Execute(null);
    }
    }

{% endhighlight %}
{% endtabs %}

![Gif for Stencil Selection Commands](Stencil_Images/StencilSelectionCommands.gif)

## Navigate Between Symbols Commands

The `MoveUp`, `MoveDown`, `MoveLeft`, and `MoveRight` commands help in moving the selection of symbols accordingly. You can navigate between symbols using the arrow keys (Up, Down, Left, Right). 

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="MoveRight" Click="MoveRightBtn_Click" ToolTip="Right Arrow"></Button>
<Button Height="50" Content="MoveLeft" Click="MoveLeftBtn_Click" ToolTip="Left  Arrow"></Button>
<Button Height="50" Content="MoveUp" Click="MoveUp_Click" ToolTip="Up Arrow"></Button>
<Button Height="50" Content="MoveDown" Click="MoveDown_Click" ToolTip="Down Arrow"></Button>

{% endhighlight %}

{% highlight C# %}

    private void MoveRightBtn_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.MoveRight.Execute(null);
        }
    }

    private void MoveLeftBtn_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.MoveLeft.Execute(null);
        }
    }
    private void MoveUp_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.MoveUp.Execute(null);
        }
    }

    private void MoveDown_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.MoveDown.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}


## MoveToFirstInRow Command

The `MoveToFirstInRow` command moves selection to the first symbol in the current row of the stencil or the first symbol of the first row if none is selected. MoveToFirstInRow command can be executed by pressing the Home key.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="MoveToFirstInRow" Click="MoveToFirstInRow_Click" ToolTip="Home"></Button>

{% endhighlight %}

{% highlight C# %}

    private void MoveToFirstInRow_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.MoveToFirstInRow.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}

## MoveToLastInRow Command

The `MoveToLastInRow` command moves selection to the last symbol in the current row of the stencil or the last symbol of the last row if none is selected. MoveToLastInRow command can be executed by pressing the End key.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="MoveToLastInRow" Click="MoveToLastInRow_Click" ToolTip="End"></Button>

{% endhighlight %}

{% highlight C# %}

    private void MoveToLastInRow_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.MoveToLastInRow.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}

## MoveToFirstInColumn Command

The `MoveToFirstInColumn` command moves selection to the first symbol in the current column of the stencil or the first symbol of the first column if none is selected. MoveToFirstInColumn command can be executed by pressing the PageUp key.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="MoveToFirstInColumn" Click="MoveToFirstInColumn_Click" ToolTip="Page Up"></Button>

{% endhighlight %}

{% highlight C# %}

    private void MoveToFirstInColumn_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.MoveToFirstInColumn.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}


## MoveToLastInColumn Command

The `MoveToLastInColumn` command moves selection to the last symbol in the current column of the stencil or the last symbol of the symbol group if none is selected. MoveToLastInColumn command can be executed by pressing the PageDown key.

{% tabs %}

{% highlight Xaml%}

<Button Height="50" Content="MoveToLastInColumn" Click="MoveToLastInColumn_Click" ToolTip="Page Down"></Button>

{% endhighlight %}

{% highlight C# %}

    private void MoveToLastInColumn_Click(object sender, RoutedEventArgs e)
    {
        if (Stencil != null)
        {
            Stencil.Commands.MoveToLastInColumn.Execute(null);
        }
    }

{% endhighlight %}
{% endtabs %}

![Gif for Stencil Move Commands](Stencil_Images/StencilMoveCommands.gif)

## Removing a Particular Command from the CommandManager

Removing a command from the `CommandManager` is straightforward. To do this, you need to identify the command by its name and then remove it from the CommandManager's collection of commands.

Here is an example of how to remove a specific command from the CommandManager:

{% tabs %}
{% highlight C# %}

    // Removing a particular stencil command from the CommandManager
    if (Stencil != null)
    {
        string commandName = "SelectAll";
        commandToBeRemoved = Stencil.CommandManager.Commands.FirstOrDefault(command => command.Name.Equals(commandName));
        Stencil.CommandManager.Commands.Remove(commandToBeRemoved);
    }
    
{% endhighlight %}
{% endtabs %}

## Adding a Custom Command to the CommandManager
Adding a custom command allows you to extend the functionality of the stencil. You can define a new command, specify its gesture, and add it to the CommandManager.

Here's an example of how to add a custom command to the CommandManager:

{% tabs %}

{% highlight Xaml%}

<Button x:Name="CustomCommandBtn" Content="Custom Command" Click="CustomCommandBtn_Click" ToolTip="Custom Command"></Button>

{% endhighlight %}

{% highlight C# %}

    ICommand Custom;
    if (Stencil != null)
    {
        // Adding a custom command to the stencil CommandManager
        Custom = new Command(OnCustomCommand);
        GestureCommand customCommandGesture = new GestureCommand()
        {
            Command = Custom,
            Gesture = new Gesture
            {
                Key = Key.K,
                KeyModifiers = ModifierKeys.Control,
                KeyState = KeyStates.Down
            },
            Name = "Custom",
        };
        Stencil.CommandManager.Commands.Add(customCommandGesture);
    }

    private void CustomCommandBtn_Click(object sender, RoutedEventArgs e)
    {
        Custom.Execute(null);
    }

    private void OnCustomCommand(object obj)
    {
        // Perform Operations
        CustomCommandMessageDisplay.Text = "Custom Command Executed Successfully!";
    }

{% endhighlight %}

{% endtabs %}

