---
layout: post
title: Serialization in WPF Diagram control | Syncfusion®
description: Learn here all about Serialization support in Syncfusion® WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Serialization in WPF Diagram (SfDiagram)

Serialization is the process of converting the state of SfDiagram's objects into a stream of bytes to recreate them when needed. Such streams can be stored in a database,as a file or memory. The reverse process is called deserialization.

## Save

In SfDiagram, DataContractSerializer is used for serialization. The functionalities in DataContractSerializer are applicable to the SfDiagram serialization. It supports saving the SfDiagram into stream. The SfDiagram gets saved with all its properties. 

{% tabs %}

{% highlight C# %}

//To Save as stream in file
SaveFileDialog dialog = new SaveFileDialog();
dialog.Title = "Save XAML";
dialog.Filter = "XAML File (*.xaml)|*.xaml";
if (dialog.ShowDialog() == true)
{
    using (Stream str = File.Open(dialog.FileName, FileMode.CreateNew))
    {
        sfDiagram.Save(str);
    }
}

//To Save as memory stream
MemoryStream str = new MemoryStream();
sfDiagram.Save(str);  

{% endhighlight %}
{% endtabs %}

## Load

On deserialization, the saved stream is used to load the SfDiagram's nodes and connectors in current view. With this, you can continue working on the earlier saved SfDiagram by loading the appropriate stream.

{% tabs %}
{% highlight C# %}

//Load from saved XAML file
OpenFileDialog dialog = new OpenFileDialog();
if (dialog.ShowDialog() == true)
{
    using (Stream myStream = dialog.OpenFile())
    {
        sfDiagram.Load(myStream);
    }
}

//Load from saved memory stream
str.Position = 0;
sfDiagram.Load(str);

{% endhighlight %}

{% endtabs %}

### Has the diagram modified?

[HasChanges](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramViewModel.html#Syncfusion_UI_Xaml_Diagram_DiagramViewModel_HasChanges) property of diagram control is used to notify that the diagram has any unsaved changes. This property track all changes that are made through interaction and through the public APIs.

{% tabs %}
{% highlight xaml %}
<!--Initialize the diagram-->
<Syncfusion:SfDiagram x:Name="diagram">
</Syncfusion:SfDiagram>
<!--Initialize the button to save the diagram-->
<Button x:Name="SaveButton" Content="Save" Click="SaveButton_Click">
</Button>
{% endhighlight %}
{% highlight C# %}
//Method to promote the save dialouge box when diagram has any unsaved changes.
private void SaveButton_Click(object sender, RoutedEventArgs e)
{
    if (diagram != null && diagram.HasChanges)
    {
        MessageBoxResult messageBoxResult = MessageBox.Show(
                            "Do you want to save the Diagram?",
                            "SfDiagram",
                            MessageBoxButton.YesNo);
        if (messageBoxResult == MessageBoxResult.Yes)
        {
            SaveDiagram();
        }
    }
}

//Method to save the diagram.
private void SaveDiagram()
{
    SaveFileDialog dialog = new SaveFileDialog();
    dialog.Title = "Save XAML";
    dialog.Filter = "XAML File (*.xaml)|*.xaml";
    if (dialog.ShowDialog() == true)
    {
        File.Delete(dialog.FileName);
        using (Stream s = File.Open(dialog.FileName, FileMode.OpenOrCreate))
        {
            diagram.Save(s);
        }
    }
}
{% endhighlight %}
{% endtabs %}

## How to serialize custom properties 

In SfDiagram, you cannot serialize the Content and ContentTemplate of each and every diagramming objects. If you want to preserve the ContentTemplate of diagramming objects, keep them in resources and apply them once the diagramming objects are added to the Diagram page.  

The custom properties in custom class derived from any of our SfDiagram's interface or from any of the view model classes are serialized with the help of DataMember attribute.

{% tabs %}
{% highlight C# %}

public class NodeContent : INode
{
    [DataMember]
    public string NodeType
    {
        get;
        set;
    }
}

{% endhighlight %}
{% endtabs %}

N> SfDiagram's interface and view model classes are created without DataContract attribute. So there is no need to add DataContract attribute for a class, which is derived from them.

## How to serialize a custom class 

You can serialize a business class with the help of DataContract attribute and SfDiagram's `KnownTypes` property. You have to add DataContract attribute to serialize the whole class, which is not derived from a base class without DataContract attribute.

{% tabs %}
{% highlight C# %}

[DataContract]
public class NodeContent
{
    [DataMember]
    public string NodeType
    {
        get;
        set;
    }
}

Diagram.KnownTypes = () => new List<Type>()
{
    typeof(NodeContent)
};

{% endhighlight %}
{% endtabs %}

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Serialization)

## How to load SfDiagram's old version in new version 

You can load any of the old version SfDiagram's stream in new version with the help of upgrade method. Refer to the following code example.

{% tabs %}
{% highlight C# %}

using (Stream myStream = dialog.OpenFile())
{
    sfDiagram.Upgrade(myStream);
    sfDiagram.Load(myStream);
}

{% endhighlight %}
{% endtabs %}

## Importing and Exporting using Mermaid Syntax

The [SfDiagram](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html) supports saving diagrams in Mermaid syntax format. Mermaid is a Markdown-inspired syntax that automatically generates diagrams. With this functionality, you can easily create mind maps and flowcharts from Mermaid syntax data, simplifying the visualization of complex ideas and processes without manual drawing. Additionally, you can export your mind maps and flowcharts to Mermaid syntax, allowing for easy sharing, editing, and use across different platforms.

### Save diagram as Mermaid syntax

The [SaveDiagramAsMermaid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_SaveDiagramAsMermaid) method serializes your diagram into a Mermaid-compatible string. This method works for diagrams using Flowchart, Mind Map, or Sequence Diagram layouts. The following example shows how to save a diagram:

{% tabs %}
{% highlight C# %}

// Initialize the SfDiagram
SfDiagram Diagram = new SfDiagram();

// Initialize a layout for the diagram (example: Flowchart)
Diagram.LayoutManager = new LayoutManager()
{
    Layout = new FlowchartLayout()
    {
        Orientation = FlowchartOrientation.TopToBottom,
        YesBranchValues = new List<string> { "Yes", "True", "Y", "s" },
        YesBranchDirection = BranchDirection.LeftInFlow,
        NoBranchValues = new List<string> { "No", "N", "False", "no" },
        NoBranchDirection = BranchDirection.RightInFlow,
        HorizontalSpacing = 60,
        VerticalSpacing = 40,
    },
};

// Alternatively, initialize the model for a sequence diagram
Diagram.Model = new UMLSequenceDiagramModel()
{
    SpaceBetweenParticipants = 120,
    Participants = new ParticipantCollection
    {
        new UMLSequenceParticipant { ID = "User", Content = "User", IsActor = true },
        new UMLSequenceParticipant { ID = "System", Content = "System", IsActor = false }
    },
    Messages = new MessageCollection
    {
        new UMLSequenceMessage
        {
            ID = "MSG1",
            Content = "Login Request",
            FromParticipantID = "User",
            ToParticipantID = "System",
            Type = UMLSequenceMessageType.Synchronous
        },
        new UMLSequenceMessage
        {
            ID = "MSG2",
            Content = "Login Response",
            FromParticipantID = "System",
            ToParticipantID = "User",
            Type = UMLSequenceMessageType.Reply
        }
    }
};

// Convert the diagram to a Mermaid string.
string mermaidData = Diagram.SaveDiagramAsMermaid();

{% endhighlight %}
{% endtabs %}

### Load diagram from Mermaid syntax

You can load a [diagram](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html) from the serialized Mermaid syntax data using the [LoadDiagramFromMermaid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_LoadDiagramFromMermaid_System_String_) method. The following code illustrates how to load a diagram from a Mermaid string data.

{% tabs %}
{% highlight C# %}

// Initialize the SfDiagram
SfDiagram Diagram = new SfDiagram();

// Initialize a layout for the diagram (example: Flowchart)
Diagram.LayoutManager = new LayoutManager()
{
    Layout = new FlowchartLayout()
    {
        Orientation = FlowchartOrientation.TopToBottom,
        YesBranchValues = new List<string> { "Yes", "True", "Y", "s" },
        YesBranchDirection = BranchDirection.LeftInFlow,
        NoBranchValues = new List<string> { "No", "N", "False", "no" },
        NoBranchDirection = BranchDirection.RightInFlow,
        HorizontalSpacing = 60,
        VerticalSpacing = 40,
    },
};

// Alternatively, initialize the model for a sequence diagram
Diagram.Model = new UMLSequenceDiagramModel()
{
    SpaceBetweenParticipants = 300,
};

// Load the diagram using the Mermaid text.
Diagram.LoadDiagramFromMermaid(mermaidData);

{% endhighlight %}
{% endtabs %}

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Serialization/MermaidTextToDiagramLayout)

N> Mermaid syntax data serialization and deserialization are supported only for Flowchart, Mind Map, and Sequence Diagram layouts. Please ensure your diagram uses one of these layouts for successful data loading.

## See Also

[How to serialize the Content and ContentTemplate properties of a Node?](https://support.syncfusion.com/kb/article/11574/how-to-serialize-content-and-contenttemplate-properties-of-a-node-in-wpf-diagramsfdiagram)

[How to change the color of a node in the stencil and diagram while loading a saved file in WPF Diagram(SfDiagram)?](https://support.syncfusion.com/kb/article/18669/how-to-change-the-color-of-a-node-in-the-stencil-and-diagram-while-loading-a-saved-file-in-wpf-diagramsfdiagram)

[How to serialize the LinearGradientBrush type as a Fill value in the ShapeStyle of a Node in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18058/how-to-serialize-the-lineargradientbrush-type-as-a-fill-value-in-the-shapestyle-of-a-node-in-the-wpf-diagram-sfdiagram)

[How to serialize and deserialize the image nodes in WPF Diagram( SfDiagram) ?](https://support.syncfusion.com/kb/article/17743/how-to-serialize-and-deserialize-the-image-nodes-in-wpf-diagram-sfdiagram-)

[How to serialize multiple diagram pages in WPF Diagram?](https://support.syncfusion.com/kb/article/16204/how-to-serialize-multiple-diagram-pages-in-wpf-diagram)

[How to preserve the state of the diagram while switching tabs in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18230/how-to-preserve-the-state-of-the-diagram-while-switching-tabs-in-the-wpf-diagram-sfdiagram)