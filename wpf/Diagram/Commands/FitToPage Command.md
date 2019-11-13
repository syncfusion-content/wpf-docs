---
layout: post
title: Syncfusion | Explore the fit to page functionality with fit to page commands.
description: FitToPage command is used to bring the required Diagram or entire Diagram into the view with the help of FitToPageParameters.
platform: wpf
control: SfDiagram
documentation: ug
---

# FitToPage

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

`CanZoomIn` is used to set whether small diagram gets zoomin to whole view or not.

![CanZoomIn](Commands_Images/Commands_img18.gif)

### FitToPage 

`FitToPage` is used to enable or disable the fittopage behavior with respect to height or width.

| Values | Description |
| --- | --- |
| None | It is used disable the fittopage behavior. |
| FitToHeight | It is used to enable the fittopage behavior only with respect to height. |
| FitToWidth | It is used to enable the fittopage behavior only with respect to width. |
| FitToPage | It is used to enable the fittopage behavior with respect to both height and width of the diagram. |

![FitToPage](Commands_Images/Commands_img19.gif)

### Region

`Region` is used to set the region where to perform fittopage in diagram.

| Values | Description |
| --- | --- |
| Content | It is used to perform fittopage for content area only. |
| PageSettings | It is used to perform fittopage based on the pagewidth and pageheight. |
| Custom | It is used to perform fittopage for custom region. |

### FocusArea 

`FocusArea` is used to set the focus area to excute fittopage in custom region. 

![Region](Commands_Images/Commands_img20.gif)

Please find the [FittoPage sample](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Fit_to_page_command1640128507) to depict this command.