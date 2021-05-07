---
layout: post
title: Command Manager in WPF Diagram control | Syncfusion
description: Learn here all about Command Manager support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Command Manager in WPF Diagram (SfDiagram)

The [CommandManager](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CommandManager.html) is used to map the user gestures (keyboard, mouse) with SfDiagram commands and helps to include new gesture commands in SfDiagram. Refer to the following table for built-in commands with Key gesture and Mouse gesture.

List of Commands and Key Gesture:

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
| UnGroup | G | Control |
| SendToBack | [ | Control+Shift |
| SendBackward | [ | Control |
| BringToFront | ] | Control+Shift |
| BringForward | ] | Control |
| Group | G | Control |
| Ungroup | G | Control |

#### List of Commands and Key Gestures with Parameter

| Command | Key | KeyModifier | Parameter |
|---|---|---|---|
| Zoom | - | Control | new ZoomPositionParameter { ZoomCommand=ZoomCommand.ZoomOut} |
| Zoom | + | Control | new ZoomPositionParameter { ZoomCommand = ZoomCommand.ZoomIn } |
| Reset | 0 | Control | new ResetParameter { Reset = Diagram.Reset.ZoomPan } |
| FitToPage | 0 | Control+ Menu | new FitToPageParameter { FitToPage = Diagram.FitToPage.FitToPage, Margin = new Thickness(20) } |

#### List of Commands and Mouse Gesture with Parameter

| Command | Scroll State | Parameter |
|---|---|---|
| Vertical Scroll using ‘Zoom’ command | Scroll | new ZoomPointerParameter { ZoomCommand = ZoomCommand.VerticalScroll} |

#### List of Commands and Key and Mouse Gesture with Parameter

| Command | KeyModifier | Scroll State | Parameter |
|---|---|---|---|
| Horizontal Scroll using ‘Zoom’ command | Shift | Scroll | new ZoomPointerParameter { ZoomCommand = ZoomCommand.HorizontalScroll} |
| Zoom | Control | Scroll | new ZoomPointerParameter { ZoomCommand = ZoomCommand.ZoomIn `|` ZoomCommand.ZoomOut} |

N> When different commands are registered for the same key / mouse gestures, you need to handle the command while execution.

### Custom command

CommandManager provides support to define custom commands. The custom commands are executed when the specified key gesture is recognized.
The [GestureCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GestureCommand.html) and [Gesture](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Gesture.html) help you to define a custom command.

The following code example represents how to define custom command to Save Command (Control + S).


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
