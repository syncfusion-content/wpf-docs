---
layout: post
title: Undo and Redo in WPF Diagram control | Syncfusion
description: Learn here all about Undo and Redo support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Undo and Redo in WPF Diagram (SfDiagram)

Diagram provides built-in support to track the changes that are made through interaction and through public APIs. The changes can be reverted or restored either through shortcut keys or through commands.

## Undo and Redo actions

Diagram tracks the history of actions that are performed after initializing the diagram and provides support to reverse and restore those changes.

The redo function restores any actions that have been previously undone using an undo
Undo is a function performed to reverse the action of an earlier action.

Undo/redo actions can be executed through shortcut keys. Shortcut key for undo is Ctrl+z and shortcut key for redo is Ctrl+y. 

Undo/Redo for diagram can be enabled/disabled with the [Constraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Constraints) property of SfDiagram class.

{% tabs %}

{% highlight xaml %}
<!--Initialize SfDiagram with undo/redo constraint-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,Undoable">
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the undo and reso actions
diagram.Constraints = GraphConstraints.Default | GraphConstraints.Undoable;
{% endhighlight %}

{% endtabs %}

Undo/redo actions can be executed using commands of diagram control instead of using short cut keys.

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram with undo constraint-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,Undoable">
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the undo and redo actions
diagram.Constraints = GraphConstraints.Default | GraphConstraints.Undoable;

//To perform the Undo action in Diagram
(diagram.Info as IGraphInfo).Commands.Undo.Execute(null);

//To Perform the Redo action in Diagram
(diagram.Info as IGraphInfo).Commands.Redo.Execute(null);
{% endhighlight %}
{% endtabs %}

## History actions

The `Action` property of the `HistoryEntry` class is used to store the history of actions performed after initializing the diagram. Changing the size of a node, dragging a connection, deleting a node, clicking and dragging the mouse, and so on are some of the actions. These types of actions are saved as `Action` properties that can be performed. This property has the following actions:

|HistoryAction|Description|
|--|--|
|None|Specifies the default value for the action type|
|PositionChanged|Specifies the element's position changed action|
|RotationChanged|Specifies the rotation value changed action for Node, Group element|
|SizeChanged|Specifies the element's size changed action|
|CollectionChanged|Specifies the diagram element's collection changed action that new element added or deleted|
|ConnectorSourceChanged|Specifies the connector element's source value changed action|
|ConnectorTargetChanged|Specifies the connector element's target value changed action|
|CustomAction|Specifies the custom element changed action|

## Entry mode

`Mode` property of `HistoryEntry` class allows to know where the changed action comes from. The `Mode` property has following type of sources,

The `Mode` property of the HistoryEntry class allows you to know whether the source of action entry is internal or external. Internal source action is accomplished by using the SfDiagram control and its elements, while external source action is accomplished by the external application users. This property has following type of sources:

|EntryMode|Description|
|--|--|
|Internal|Specifies source of action entry is added internally by SfDiagram to the undo-redo stack |
|External|Specifies source of action is added externally by the user to the undo-redo stack|

## Stack limit

The `StackLimit` property of `HistoryManager` class allows you to specify a stack limit value, which is used to limit the maximum number of history entries that can be stored in the Undo and Redo stacks.

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram with undo and redo constraint-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,Undoable">
    <Syncfusion:SfDiagram.HistoryManager>
        <Syncfusion:HistoryManager StackLimit="3"/>
    </Syncfusion:SfDiagram.HistoryManager>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the undo and redo actions
diagram.Constraints = GraphConstraints.Default | GraphConstraints.Undoable;
diagram.HistoryManager = new HistoryManager()
{
    StackLimit = 3,
};
{% endhighlight %}
{% endtabs %}

## Start group action

The `BeginComposite()` method of `HistoryManager` class allows you to log multiple actions at a time in the history manager stack. It is easier to undo or revert the changes made in the diagram in a single undo/redo process instead of reverting every actions one by one.

{% tabs %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the undo and redo actions
diagram.Constraints = GraphConstraints.Default | GraphConstraints.Undoable;
//Initialize the history manager class
diagram.HistoryManager = new HistoryManager();
//method to initiate the group action
diagram.HistoryManager.BeginComposite();
{% endhighlight %}
{% endtabs %}

## End group action

The `EndComposite()` method of the `HistoryManager` class allows you to end the group actions that are stored in the stack history.

{% tabs %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the undo and redo actions
diagram.Constraints = GraphConstraints.Default | GraphConstraints.Undoable;
//Initialize the history manager class
diagram.HistoryManager = new HistoryManager();
//method to stop the group action
diagram.HistoryManager.EndComposite();
{% endhighlight %}
{% endtabs %}

![Start end group action](HistoryManager_images/StartEndGroupAction.gif)

## How to view Undo/Redo stack

History manager class of SfDiagram control allows you to view the undo and redo stack values where you can get what the actions, values, and elements are stored in the history manager stack by using the `HistoryChangedEventArgs` argument value of `HistoryChangedEvent` event.

{% tabs %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Hook the history changed event.
(diagram.Info as IGraphInfo).HistoryChangedEvent += HistoryChangedEvent;
 private void HistoryChangedEvent(object sender, HistoryChangedEventArgs args)
{
    UndoText = string.Empty;
    foreach (HistoryEntry entry in HistoryManager.UndoStack as Stack<HistoryEntry>)
    {
        if (UndoText == string.Empty)
        {
            UndoText = "Action: " + entry.Action.ToString();
            UndoText = UndoText + "\n" + "Mode: " + entry.Mode.ToString();
        }
        else
        {
            UndoText = UndoText+ "\n" + "Action: " + entry.Action.ToString();
            UndoText = UndoText + "\n" + "Mode: " + entry.Mode.ToString();
        }
    }

    RedoText = string.Empty;
    foreach (HistoryEntry entry in HistoryManager.RedoStack as Stack<HistoryEntry>)
    {
        if (RedoText == string.Empty)
        {
            RedoText = "Action: " + entry.Action.ToString();
            RedoText = RedoText + "\n" + "Mode: " + entry.Mode.ToString();
        }
        else
        {
            RedoText = RedoText + "\n" + "Action: " + entry.Action.ToString();
            RedoText = RedoText + "\n" + "Mode: " + entry.Mode.ToString();
        }
    }
}
{% endhighlight %}
{% endtabs %}

![Undo redo stack view](HistoryManager_images/UndoRedoStackView.png)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/HistoryManager/HistoryManagerStackView)

## How to log custom actions in undo/redo stack

History list allows to revert or restore single and multiple changes through a single undo/redo command. The purpose of custom undo redo process is to store actions which are not done through default undo redo history list. Appearance level changes and its history informations did not stored in the history list.  For example, revert/restore the fill color change of multiple elements at a time. To store multiple actions at a time, actions should be logged using [CompositeTransactions](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CompositeTransactions.html) class.

To achieve this you need to customize the [HistoryManager](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.HistoryManager.html) class of diagram control and need to override the Undo Redo methods.

{% tabs %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Assigning the custom history manager class
diagram.HistoryManager = new HistoryManager();

//To change the nodes fill color into blue and logging the action into history manager class.
diagram.HistoryManager.BeginComposite();
foreach (NodeVm node in ((IEnumerable<object>)(diagram.SelectedItems as SelectorViewModel).Nodes))
{
    if (node is NodeVm)
    {
        (node as NodeVm).Fill = new SolidColorBrush(Colors.CornflowerBlue);
    }
}
//To stop the group action stored in the undo/red stack
diagram.HistoryManager.EndComposite(diagram.HistoryManager, end);

//Creating custom node view model to update the fill property to nodes
public class NodeVm : NodeViewModel, IUndoRedo
{
    public NodeState _mCollectionData;

    public NodeVm()
    {
        _mCollectionData = new NodeState( Fill);
    }

    private Brush _mFill = new SolidColorBrush(Colors.Black);

    //Creating fill property to node to get or set the fill color for node
    public Brush Fill
    {
        get
        {
            return _mFill;
        }
        set
        {
            if (_mFill != value)
            {
                _mFill = value;
                OnPropertyChanged(NodeConstants.Fill);
            }
        }
    }

    //Allows to store the fill color data 
    private bool AllowToLogData(string name)
    {
        if (name == "Fill")
        {
            return true;
        }

        return false;
    }

    //To store the actions performed
    public void LogData(object data)
    {
        var info = this.Info as INodeInfo;
        if (info != null && info.Graph != null )
        {
            info.Graph.HistoryManager.LogData(this, data);   
        }
    }

    //To apply the fill color to the node when undo/redo
    private void OnFillChanged()
    {
        Style s = new Style(typeof(Path));
        if (Fill != null)
        {
            s.Setters.Add(new Setter(Path.FillProperty, Fill));
            s.Setters.Add(new Setter(Path.StretchProperty, Stretch.Fill));
        }
        ShapeStyle = s;
    }

    //To update the fill property when it is changed
    protected override void OnPropertyChanged(string name)
    {
        var info = this.Info as INodeInfo;
        if (info != null && info.Graph != null && info.Graph.HistoryManager != null && AllowToLogData(name))
        {

            if (info.Graph.HistoryManager.CanLogData(info.Graph.HistoryManager, _mCollectionData))
            {
                LogData(_mCollectionData);
            }
        }
        base.OnPropertyChanged(name);
        switch (name)
        {
            case NodeConstants.Fill:
                OnFillChanged();
                _mCollectionData.Fill = this.Fill;
                break;
        }
    }

    public UndoRedoState State { get; set; }

    public bool CanRedo(object data)
    {
        if (State == UndoRedoState.Idle)
        {
            return true;
        }
        return false;
    }

    public bool CanUndo(object data)
    {
        if (State == UndoRedoState.Idle)
        {
            return true;
        }
        return false;
    }

    public object Undo(object data)
    {
        if (data is NodeState)
        {
            return RevertTo(data);
        }
        else
            return data;
    }

    public object Redo(object data)
    {
        if (data is NodeState)
        {
            return RevertTo(data);
        }
        else
            return data;
    }

    public object RevertTo(object data)
    {
        if (data is NodeState)
        {
            var current = GetData();
            NodeState toState = (NodeState)data;
            if (toState.Fill != this.Fill)
            {
                this.Fill = toState.Fill;
            }
            return current;
        }
        return data;
    }

    public object GetData()
    {
        return _mCollectionData;
    }
}

//Create class for node constants value
internal static class NodeConstants
{
    public const string Fill = "Fill";
}

//To specify the fill state for nodes.
public struct NodeState
{
    private Brush _mFill;
    public Brush Fill
    {
        get
        {
            return _mFill;
        }
        set
        {
            if (_mFill != value)
            {
                _mFill = value;
            }
        }
    }
    public NodeState(Brush fill)
    {
        _mFill = fill;
    }
}
{% endhighlight %}
{% endtabs %}

![Custom undo redo](HistoryManager_images/CustomUndoRedo.gif)

## How to restrict Undo/Redo

Undo, Redo process can be avoided for particular element by using [CanLogHistoryEntry](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_CanLogHistoryEntry_Syncfusion_UI_Xaml_Diagram_LogDataArgs_) virtual method of diagram control.

{% tabs %}
{% highlight C# %}
//Initialize the custom diagram class
CustomDiagram diagram = new CustomDiagram();

//Create custom node class to add can log property
public class NodeVm : NodeViewModel, IUndoRedo
{
    private bool canlog = true;

    //Specifies undo/redo process is enabled or disabled for a node
    public bool CanLogmultipleselect
    {
        get
        {
            return canlog;           
        }
        set
        {
            if (value != canlog)
            {
                canlog = value;
                OnPropertyChanged("CanLogmultipleselect");
            }
        }
    }
}
//Create the custom SfDiagram class
public class CustomDiagram: SfDiagram
{
    //Overriding the method to avoid actions stored
    protected override bool CanLogHistoryEntry(LogDataArgs item)
    {
        if (item.Item is NodeVm)
        {
            if (!(item.Item as NodeVm).CanLogmultipleselect)
            {
                return false;
            }
            return base.CanLogHistoryEntry(item);
        }
        else
            return base.CanLogHistoryEntry(item);
    }
}
{% endhighlight %}
{% endtabs %}

![HistoryManager](HistoryManager_images/Canlog.gif)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/HistoryManager/CustomHistoryManger)

## History changed event

History manager class of `SfDiagram` control provides `HistoryChangedEvent` and `HistoryChangedCommand` to notify while there is a change in undo/redo stack values.

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram with undo and redo constraint-->
<syncfusion:SfDiagram x:Name="diagram" Constraints="Default,Undoable" 
HistoryChangedCommand="{Binding HistoryChangedCommand}">
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Enable the undo and redo actions
diagram.Constraints = GraphConstraints.Default | GraphConstraints.Undoable;
//Hook history changed event
(diagram.Info as IGraphInfo).HistoryChangedEvent += HistoryChangedEvent;
private void HistoryChangedEvent(object sender, HistoryChangedEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

## Events for Undo Redo Process

Diagram allows to notify undo/redo action for the below events,

* [NodeChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_NodeChangedEvent)
* [ItemDeletedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemDeleted)
* [ItemAddedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ItemAdded)
* [PortChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_PortChanged)
* [AnnotationChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_AnnotationChanged)
* [ConnectorSourceChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ConnectorSourceChangedEvent)
* [ConnectorTargetChangedEvent](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ConnectorTargetChangedEvent)
* [ViewPortChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IGraphInfo.html#Syncfusion_UI_Xaml_Diagram_IGraphInfo_ViewPortChanged)

{% tabs %}
{% highlight C# %}
//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Register the node changed event
(diagram.Info as IGraphInfo).NodeChangedEvent += Diagram_NodeChangedEvent;

private void Diagram_NodeChangedEvent(object sender, ChangeEventArgs<object, NodeChangedEventArgs> args)
{
    MessageBox.Show(args.Cause.ToString());
}
{% endhighlight %}
{% endtabs %}

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/HistoryManager/HistoryManagerDemoSample)

## See Also

* [How to add enable undo and redo using commands?](/wpf/sfdiagram/commands/undoredo)
