---
layout: post
title: FitToPage Command in WPF SfDiagram | Syncfusion®
description: Fit diagram content within the view in Syncfusion® WPF SfDiagram using FitToPage commands and customizable fitting parameters.
platform: wpf
control: SfDiagram
documentation: ug
---

# FitToPage Command in WPF SfDiagram

The [FitToPage](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_FitToPage) command is used to bring the entire diagram into view. The [FitToPageParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.FitToPageParameter.html) parameter is used to customize the `FitToPage` command behavior. If the parameter is null, the entire diagram fits into view.

{% tabs %}

{% highlight xaml%}

<Button Height="50" Content="FitToPage" Name="FitToPage" Command="Syncfusion:DiagramCommands.FitToPage"></Button>

{% endhighlight %}

{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// To fit the Diagram into the view
graphinfo.Commands.FitToPage.Execute(null);

{% endhighlight %}
{% endtabs %}

## FitToPageParameter

The `FitToPageParameter` parameter is used to customize the `FitToPage` command behavior. If the parameter is null, the entire diagram fits into the view.

### CanZoomIn

The [CanZoomIn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.FitToPageParameter.html#Syncfusion_UI_Xaml_Diagram_FitToPageParameter_CanZoomIn) is used to set whether small diagrams are zoomed to fit the view or not.

![CanZoomIn](Commands_Images/Commands_img18.gif)

### FitToPage 

The [FitToPage](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.FitToPageParameter.html#Syncfusion_UI_Xaml_Diagram_FitToPageParameter_FitToPage) is used to enable or disable the fit to page behavior with respect to height or width.

| Values | Description |
| --- | --- |
| None | It is used to disable the FitToPage behavior. |
| FitToHeight | It is used to enable the fit to page behavior only with respect to height. |
| FitToWidth | It is used to enable the fit to page behavior only with respect to width. |
| FitToPage | It is used to enable the fit to page behavior with respect to both height and width of the diagram. |

![FitToPage](Commands_Images/Commands_img19.gif)

### Region

The [Region](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.FitToPageParameter.html#Syncfusion_UI_Xaml_Diagram_FitToPageParameter_Region) is used to set the region where the `FitToPage` command should be applied in the diagram.

| Values | Description |
| --- | --- |
| Content | It is used to perform fit to page for the content area only. |
| PageSettings | It is used to perform fit to page based on the page width and page height. |
| Custom | It is used to perform fit to page for custom region. |

N> When the `Region` property is set to `Custom`, you must define the `FocusArea` property to specify the region that should be fitted into the view. Without a valid `FocusArea`, the custom fit-to-page operation cannot determine the target region.

### FocusArea 

The [FocusArea](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.FitToPageParameter.html#Syncfusion_UI_Xaml_Diagram_FitToPageParameter_FocusArea) is used to set the focus area to execute the `FitToPage` command in a custom region. 

The following example shows how to create a `FitToPageParameter` instance and pass it to the `FitToPage` command.

{% tabs %}
{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagram = new SfDiagram();

IGraphInfo graphinfo = diagram.Info as IGraphInfo;

graphinfo.Commands.FitToPage.Execute(
    new FitToPageParameter()
    {
        // To fit the diagram with respect to both width and height.
        FitToPage = FitToPage.FitToPage
    });

{% endhighlight %}
{% endtabs %}

![Region](Commands_Images/Commands_img20.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Fit%20to%20page%20command)

## See Also
 
[How to apply margin values to FitToPage command?](https://support.syncfusion.com/kb/article/5474/how-to-apply-margin-to-fittopage-in-wpf-diagram-sfdiagram)

[How to Fit Selected Nodes and Connectors to the WPF Diagram Window?](https://support.syncfusion.com/kb/article/18062/how-to-fit-selected-nodes-and-connectors-to-the-wpf-diagram-window)