---
layout: post
title: Command Manager in WPF SfDiagram | Syncfusion®
description: Map keyboard and mouse gestures to commands in Syncfusion® WPF SfDiagram and create custom commands with Command Manager.
platform: wpf
control: SfDiagram
documentation: ug
---

# Command Manager in WPF SfDiagram

The [CommandManager](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CommandManager.html) is used to map user gestures (keyboard and mouse) to SfDiagram commands and helps to include new gesture commands in [WPF Diagram](https://www.syncfusion.com/diagram-sdk/wpf-diagram). 

The `CommandManager` can be accessed through the `SfDiagram` instance and is used to manage built-in and custom gesture commands.

{% highlight C# %}

// Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();

// Access the CommandManager
CommandManager commandManager = diagram.CommandManager;

{% endhighlight %}

Refer to the following table for built-in commands with Key gesture and Mouse gesture.

List of Commands and Key Gestures:

| Command | Key | Key Modifiers |
|---|---|---|
| Copy | C | Control |
| Cut | X| Control |
| Paste | V | Control |
| Duplicate | D | Control |
| Undo | Z | Control |
| Redo | Y | Control |
| MoveLeft | Left | |	
| MoveRight | Right | |
| MoveUp | Up |	|
| MoveDown | Down |	|
| Delete | Delete |	|
| SelectAll | A	| Control |
| Group| G|	Control |
| UnGroup | U | Control+Shift |
| SendToBack | [ | Control+Shift |
| SendBackward | [ | Control |
| BringToFront | ] | Control+Shift |
| BringForward | ] | Control |

## List of Commands and Mouse Gestures with Parameters

| Command | Key | KeyModifier | Parameter |
|---|---|---|---|
| Zoom | - | Control | new ZoomPositionParameter { ZoomCommand=ZoomCommand.ZoomOut} |
| Zoom | + | Control | new ZoomPositionParameter { ZoomCommand = ZoomCommand.ZoomIn } |
| Reset | 0 | Control | new ResetParameter { Reset = Diagram.Reset.ZoomPan } |
| FitToPage | W | Control + Shift | new FitToPageParameter { FitToPage = Diagram.FitToPage.FitToPage, Margin = new Thickness(20) } |

## List of Commands and Mouse Gestures with Parameters

| Command | Scroll State | Parameter |
|---|---|---|
| Vertical Scroll using ‘Zoom’ command | Scroll | new ZoomPointerParameter { ZoomCommand = ZoomCommand.VerticalScroll} |

## List of Commands and Key and Mouse Gestures with Parameter

| Command | KeyModifier | Scroll State | Parameter |
|---|---|---|---|
| Horizontal Scroll using ‘Zoom’ command | Shift | Scroll | new ZoomPointerParameter { ZoomCommand = ZoomCommand.HorizontalScroll} |
| Zoom | Control | Scroll | new ZoomPointerParameter { ZoomCommand = ZoomCommand.ZoomIn | ZoomCommand.ZoomOut} |

N> When multiple commands are registered for the same key or mouse gesture, gesture conflicts can occur. In such cases, handle the command execution logic to determine which command should be executed for the registered gesture.

N> The built-in key and mouse gestures are scoped to the `SfDiagram` control and are available when the diagram has input focus. These gestures do not apply globally across the application.

### Custom command

`CommandManager` provides support to define custom commands. The custom commands are executed when the specified key gesture is recognized. The [GestureCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GestureCommand.html) and [Gesture](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Gesture.html) help you to define a custom command.

N> In the following example, `Save` represents a user-defined `ICommand` instance that must be created before registering it with the `CommandManager`.

The following code example represents how to define a custom Save command (Control + S).


{% tabs %}
{% highlight C# %}

// To define the mouse and keyboard gesture for the commands
GestureCommand saveGesture = new GestureCommand()
{
    // Define the command with custom command
    Command = Save,
    // Define gesture for custom Command
    Gesture = new Gesture
    {
        KeyModifiers = ModifierKeys.Control,
        KeyState = KeyStates.Down,
        Key = Key.S
    },
    // Parameter for command - file name for save command
    Parameter = "diagram"
};

// Add the custom command to the existing command collection.
diagram.CommandManager.Commands.Add(saveGesture);

{% endhighlight %}
{% endtabs %}

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/CustomCommand)

## See Also

[How to map the custom commands to existing gestures (keyboard shortcuts and mouse)?](https://support.syncfusion.com/kb/article/8709/how-to-map-the-custom-commands-to-existing-gestures-keyboard-shortcuts-and-mouse-in-wpf)

[How to add a custom gesture command in the WPF Diagram (SfDiagram )?](https://support.syncfusion.com/kb/article/18237/how-to-add-a-custom-gesture-command-in-the-wpf-diagram-sfdiagram-)