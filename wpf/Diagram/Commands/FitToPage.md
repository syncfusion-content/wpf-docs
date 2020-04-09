---
layout: post
title: Syncfusion | Explore the FitToPage commands.
description: FitToPage command is used to bring the required Diagram or entire Diagram into the view with the help of FitToPageParameters.
platform: wpf
control: SfDiagram
documentation: ug
---

# FitToPage in WPF Diagram(SfDiagram)

FitToPage commands are used to bring the entire Diagram into the view. [IFitToPage parameter](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.FitToPageParameter_members.html) is used to customize the FitToPage command behavior.
If the parameter is null, entire Diagram is fit into the view.

{% tabs %}
{% highlight C# %}

IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;
// To fit the Diagram into the view
graphinfo.Commands.FitToPage.Execute(null);

{% endhighlight %}
{% endtabs %}

## FitToPageParameter

[IFitToPage parameter](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.FitToPageParameter_members.html) is used to customize the FitToPage command behavior.

### CanZoomIn

`CanZoomIn` is used to set whether small diagram gets zoom in to whole view or not.

![CanZoomIn](Commands_Images/Commands_img18.gif)

### FitToPage 

`FitToPage` is used to enable or disable the fit to page behavior with respect to height or width.

| Values | Description |
| --- | --- |
| None | It is used disable the fit to page behavior. |
| FitToHeight | It is used to enable the fit to page behavior only with respect to height. |
| FitToWidth | It is used to enable the fit to page behavior only with respect to width. |
| FitToPage | It is used to enable the fit to page behavior with respect to both height and width of the diagram. |

![FitToPage](Commands_Images/Commands_img19.gif)

### Region

`Region` is used to set the region where to perform fittopage in diagram.

| Values | Description |
| --- | --- |
| Content | It is used to perform fit to page for content area only. |
| PageSettings | It is used to perform fit to page based on the page width and page height. |
| Custom | It is used to perform fit to page for custom region. |

### FocusArea 

`FocusArea` is used to set the focus area to execute `FitToPage` command in custom region. 

![Region](Commands_Images/Commands_img20.gif)

Please find the [Fit to page sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Fit%20to%20page%20command) to depict this command.