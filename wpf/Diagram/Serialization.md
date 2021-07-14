---
layout: post
title: Serialization in WPF Diagram control | Syncfusion
description: Learn here all about Serialization support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
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
<!--Initialize the stencil-->
<Syncfusion:SfDiagram x:Name="diagram">
</Syncfusion:SfDiagram>
<!--Initialize the stencil-->
<Button x:Name="SaveButton" Content="Save" Click="SaveButton_Click">
</Button>
{% endhighlight %}
{% highlight C# %}
//Method to promote save dialouge box when diagram has any unsaved changes.
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

In SfDiagram, you cannot serialize Content, ContentTemplate, Shape, and ShapeStyle of each and every diagramming objects. If you want to preserve the ShapeStyle and ContentTemplate of diagramming objects, keep them in resources and apply once the diagramming objects are added to the Diagram page.  

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

You can serialize a business class with the help of DataContract attribute and SfDiagram's KnownTypes property. You have to add DataContract attribute to serialize the whole class, which is not derived from a base class without DataContract attribute.

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
