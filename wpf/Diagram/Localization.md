---
layout: post
title: Localization in WPF Diagram control | Syncfusion
description: Learn here all about Localization support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Localization in WPF Diagram (SfDiagram)

Localization is the process of configuring the application to a specific language. `SfDiagram` provides support to localize all the static text used for annotation and context menu contents.

![Localization](Localization_images/Localization_img1.png)

You can refer [Localization](https://help.syncfusion.com/wpf/localization) to add [resource file](https://msdn.microsoft.com/library/aa992030.aspx) in the application.

## Localize the Annotations using ResourceManager

SfDiagram has support to localize the Annotations of Nodes/Connector.The following code illustrates how to provide localization support for Annotation.

{% tabs %}
{% highlight xaml %}
<!--Style for Node-->
<Style TargetType="Path" x:Key="Nodestyle">
    <Setter Property="Stretch" Value="Fill"/>
    <Setter Property="Fill" Value="#FF5B9BD5"/>
</Style>   
{% endhighlight %}


{% highlight c# %}
public MainWindow()
{    
    System.Resources.ResourceManager manager;
    //Get CultureInfo 
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("fr");//French

    //Initialize Assembly
    Assembly assembly = Application.Current.GetType().Assembly;
    manager = new System.Resources.ResourceManager("Localization.Resources.Syncfusion.SfDiagram.WPF", assembly);
    InitializeComponent();

    //Creating Diagram
    SfDiagram diagram = new SfDiagram();

    //Adding diagram to the main grid of the mainwindow.
    RootGrid.Children.Add(diagram);
    
    diagram.Nodes =new ObservableCollection<NodeViewModel>();

    NodeViewModel node = new NodeViewModel();
    node.UnitWidth = 150;
    node.UnitHeight = 60;
    node.OffsetX = 345;
    node.OffsetY = 140;
    node.Annotations = new ObservableCollection<IAnnotation>()
    {
        new AnnotationEditorViewModel()
        {
            //localizing annotation using ResourceManager
            Content = manager.GetString("NewIdea"),
        }
    };
    node.Shape = new EllipseGeometry() { RadiusX = 100, RadiusY = 100 };
    node.ShapeStyle = this.Resources["Nodestyle"] as Style;
    (diagram.Nodes as ObservableCollection<NodeViewModel>).Add(node);

}   
{% endhighlight %}
{% endtabs %}

![Localized node](Localization_images/Localization_img5.png)

N> You have to define the textual descriptions of the context menu items for your custom cultures.

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Localization)






