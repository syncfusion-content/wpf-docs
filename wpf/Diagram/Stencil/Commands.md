---
layout: post
title: Commands Support for Stencil in WPF Diagram control | Syncfusion
description: Learn here all about keyboard commands support for Stencil in Syncfusion WPF Diagram (SfDiagram) control ports.
platform: wpf
control: SfDiagram
documentation: ug
---

# Keyboard Commands Support for Stencil in WPF Diagram (SfDiagram)

The Stencil in the WPF Diagram (SfDiagram) library now supports a variety of keyboard commands. These commands allow users to perform actions such as navigating through symbols, selecting multiple symbols, and performing clipboard operations—all without leaving the keyboard.

### Key Features

1. **Navigation with Arrow Keys**
   - Users can now navigate through symbols in the stencil using the arrow keys. This allows for quick and efficient selection of adjacent symbols without using a mouse.

2. **Home and End Keys for Row Navigation**
   - Pressing the Home key moves the selection focus to the first symbol in the current row of the stencil.
   - Pressing the End key moves the selection focus to the last symbol in the current row.

3. **Page Up and Page Down for Column Navigation**
   - Pressing the Page Up key shifts the focus to the first symbol in the current column.
   - Pressing the Page Down key moves the focus to the last symbol in the current column.

4. **Clipboard Operations**
   - **Cut (Ctrl+X):** Cuts the selected symbols to the clipboard.
   - **Copy (Ctrl+C):** Copies the selected symbols to the clipboard.
   - **Paste (Ctrl+V):** Pastes the contents from the clipboard into the stencil.
   - **Delete:** Deletes the selected symbols from the symbol group.

5. **Select All and Cancel Selection**
   - **Select All (Ctrl+A):** Selects all symbols in the selected symbol group. Note that this command does not work if the symbol selection mode is set to single.
   - **Cancel Selection (Esc):** Unselects the currently selected symbols.

6. **Custom Command Execution**
   - Custom commands enable users to create and execute specialized actions within stencil interactions, enhancing flexibility beyond standard commands.

### Implementation Details

To enable these keyboard shortcuts in your application, ensure that the SfDiagram library is updated to the latest version. Below are code snippets demonstrating how to execute these commands in XAML and C#:

### Move between symbols in a stencil using Arrow keys

Move between symbols by using Arrow keys (MoveUp, MoveDown, MoveLeft, MoveRight). Here's the code to execute these stencil commands from the code-behind.

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


### Move to the first symbol in a row of a stencil's symbol group using Home key

The `MoveToFirstInRow` command moves selection focus to the first symbol in the current row of the stencil or the first symbol of the first row if none is selected. Here's the code to execute this stencil commands from the code-behind.

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

### Move to the last symbol in a row of a stencil using End key

The `MoveToLastInRow` command moves selection focus to the last symbol in the current row of the stencil or the last symbol of the last row if none is selected. Here's the code to execute this stencil command from the code-behind.

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

### Move to the first symbol in a column of a stencil using Page Up key

The `MoveToFirstInColumn` command moves selection focus to the first symbol in the current column of the stencil or the first symbol of the first column if none is selected. Here's the code to execute this stencil command from the code-behind.

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


### Move to the last symbol in a column of a stencil using Page Down key

The `MoveToLastInColumn` command moves selection focus to the last symbol in the current column of the stencil or the last symbol of the symbol group if none is selected. Here's the code to execute this stencil command from the code-behind.

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

![Gif for Stencil Move Commands](Stencil_Images/Stencil_Move_Commands.gif)

### Cut the selected symbols to the clipboard using Ctrl+X

The `Cut` command removes the selected symbol from the stencil and stores it on the clipboard.

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

### Copy the selected symbols to the clipboard using Ctrl+C

The `Copy` command copies the selected symbol from the stencil and stores it on the clipboard.

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

### Paste the contents of the clipboard to a new stencil using Ctrl+V

The `Paste` command inserts the symbol into the symbol group that was previously stored in the clipboard.

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


### Delete the selected symbols using Delete Key

The `Delete` command removes the selected symbol from the symbol group.

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

![Gif for Stencil Clipboard Commands](Stencil_Images/Stencil_Clipboard_Commands.gif)

### Select all the symbols in a stencil using Ctrl+A

The `SelectAll` command selects all symbols in the symbol group.

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


### Cancel the selection of symbols in a stencil using Esc

The `UnSelect` command deselects any currently selected symbol in the stencil.

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

![Gif for Stencil Selection Commands](Stencil_Images/Stencil_Selection_Commands.gif)

### Command Manager for Stencil
The CommandManager for the Stencil component in WPF allows you to map user gestures (keyboard) to stencil commands, add new gesture commands, and remove existing commands. This functionality enhances the flexibility and usability of the stencil.

#### Built-in Commands and Key Gestures
The Stencil's CommandManager provides a range of built-in commands that can be executed using specific key gestures. Here is a list of common commands and their corresponding key gestures:

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
| MoveToFirstInColumn | Page Up ||
| MoveToLastInColumn | Page Down ||

#### Removing a Particular Command from the CommandManager
Removing a command from the CommandManager is straightforward. You can identify the command by its name and then remove it from the CommandManager's collection of commands.

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

#### Adding a Custom Command to the CommandManager
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

