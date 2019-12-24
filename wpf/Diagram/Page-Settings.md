---
layout: post
title: Size and appearance customization of Diagram pages | Syncfusion
description: How to customize the size and appearance of the Diagram pages and how to split the single page into multiple pages?
platform: wpf
control: SfDiagram
documentation: ug
---

# Page Settings

By default, Diagram's page size is decided based on the position of diagramming elements. The size and appearance of the diagram pages can be customized with help of [PageSettings](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.PageSettings.html "PageSettings") property of SfDiagram. 

* The `PageWidth` and `PageHeight` properties of `PageSettings` define the size of the page. 
* The `PageOrientation` property of `PageSettings` used to change the page orientation to portrait or landscape.
* Page breaks is used as a visual guide to see how pages are split into multiple pages. The `ShowPageBreaks` property will decide on Visibility of Page breaks.

{% tabs %}
{% highlight xaml %}

<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the page settings and page orientation property-->
  <syncfusion:SfDiagram.PageSettings>
    <syncfusion:PageSettings PageOrientation="Portrait" PageWidth="300" PageHeight="400" ShowPageBreaks="True" />
  </syncfusion:SfDiagram.PageSettings>
</syncfusion:SfDiagram>

{% endhighlight %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();

//Initialize the page settings and and page orientation property
diagram.PageSettings = new PageSettings()
{
  PageOrientation = PageOrientation.Portrait,
  PageWidth = 300,
  PageHeight = 400,
  ShowPageBreaks = true,
};
{% endhighlight %}
{% endtabs %}

| Page Orientation | Output |
|---|---|
| Landscape | ![Landscape](Page-Settings_images/Landscape.png) |
| Portrait | ![Portrait](Page-Settings_images/Portrait.png) |

## How to enable the multiple page

Based on Diagramming element position, the size of the page dynamically increases or decreases in multiples of page width and height with help of `MultiplePage` property of PageSettings.

{% tabs %}
{% highlight xaml %}

<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the page settings and its properties-->
  <syncfusion:SfDiagram.PageSettings>
    <syncfusion:PageSettings PageWidth="500" PageHeight="500" MultiplePage="True" ShowPageBreaks="True" />
  </syncfusion:SfDiagram.PageSettings>
</syncfusion:SfDiagram>

{% endhighlight %}
{% highlight C# %}

//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the page settings and its properties
diagram.PageSettings = new PageSettings()
{
    PageHeight = 300,
    PageWidth = 300,
    MultiplePage = true,
    ShowPageBreaks = true,
};
            
{% endhighlight %}
{% endtabs %}

![Multiple Pages](Page-Settings_images/MultiplePages.png)


## How to change the page appearance

The appearance of the pages can be customized by using following properties of `PageSettings` class,

* `PageBorderThickness`: Defines the thickness of the  border around the entire page.
* `PageBackground`: Defines the background colors of the page.
* `PageBorderBrush`: Defines the color of the page border

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the page settings and its properties-->
  <syncfusion:SfDiagram.PageSettings>
    <syncfusion:PageSettings PageBorderThickness="5" PageBackground="LightGreen" PageBorderBrush="Black" PageWidth="500" PageHeight="500" MultiplePage="True" ShowPageBreaks="True" />
  </syncfusion:SfDiagram.PageSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the page settings and its properties
diagram.PageSettings = new PageSettings()
{
  PageBorderThickness = new Thickness(5),
  PageBackground = new SolidColorBrush(Colors.LightGreen),
  PageBorderBrush = new SolidColorBrush(Colors.Black),
  PageWidth = 300,
  PageHeight = 300,
  MultiplePage = true,
  ShowPageBreaks = true,
};
            
{% endhighlight %}
{% endtabs %}

![Appearance](Page-Settings_images/Appearance.png)

## How to change the margin around the pages

The area between the main content of a page and the page edges can be changed by using `PrintMargin` property. Default value is 24.

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the page settings and print margin property-->
  <syncfusion:SfDiagram.PageSettings>
    <syncfusion:PageSettings PrintMargin="40" PageWidth="300" PageHeight="300" ShowPageBreaks="True" />
  </syncfusion:SfDiagram.PageSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the page settings and print margin property
diagram.PageSettings = new PageSettings()
{
  PrintMargin = new Thickness(40),
  PageWidth = 300,
  PageHeight = 300,
  ShowPageBreaks = true,
};
            
{% endhighlight %}
{% endtabs %}

![PrintMargin](Page-Settings_images/PrintMargin.png)

## How to change the Unit of the page

The measurement Units of the page can be changed by using `Unit` property of `PageSettings` class. Default unit value is Pixels.

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the page settings and unit property-->
  <syncfusion:SfDiagram.PageSettings>
    <syncfusion:PageSettings>
      <syncfusion:PageSettings.Unit>
        <syncfusion:LengthUnit Unit="Inches"/>
      </syncfusion:PageSettings.Unit>
    </syncfusion:PageSettings>
  </syncfusion:SfDiagram.PageSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the page settings and unit property
diagram.PageSettings = new PageSettings()
{
  Unit = new LengthUnit() { Unit = LengthUnits.Inches },
};
            
{% endhighlight %}
{% endtabs %}

| Unit values | Output |
|---|---|
| Centimeters | ![Centimeters](Page-Settings_images/UnitCms.PNG) |
| Inches | ![Inches](Page-Settings_images/UnitInches.png) |

## How to change the scaling of Page

The `PrintScale` property of `PageSettings` class will allows you to reduce or enlarge the diagram page to fit into specific area when you print it. The default scaling of the page will be 1 (i.e 100%).

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the page settings -->
  <syncfusion:SfDiagram.PageSettings>
    <syncfusion:PageSettings PrintMargin="40" PageWidth="300" PageHeight="300" ShowPageBreaks="True" MultiplePage="True" PrintScale="3" />
  </syncfusion:SfDiagram.PageSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the page settings and print scale value.
diagram.PageSettings = new PageSettings()
{
  PrintMargin = new Thickness(40),
  PageWidth = 300,
  PageHeight = 300,
  ShowPageBreaks = true,
  MultiplePage = true,
  //Specify the print scale value.
  PrintScale = 3,
};
            
{% endhighlight %}
{% endtabs %}

You can restrict the diagram page scaling to minimum and maximum values by using `MinimumPrintScale` and `MaximumPrintScale` properties.

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <!--Initialize the page settings -->
  <syncfusion:SfDiagram.PageSettings>
    <syncfusion:PageSettings PrintMargin="40" PageWidth="300" PageHeight="300" ShowPageBreaks="True" MultiplePage="True" MinimumPrintScale="2" MaximumPrintScale="4"/>
  </syncfusion:SfDiagram.PageSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the page settings and print scale value.
diagram.PageSettings = new PageSettings()
{
  PrintMargin = new Thickness(40),
  PageWidth = 300,
  PageHeight = 300,
  ShowPageBreaks = true,
  MultiplePage = true,
  //Specify the minimum and maximum print scale values.
  MinimumPrintScale = 2,
  MaximumPrintScale = 4,
};
            
{% endhighlight %}
{% endtabs %}

## How to customize the page origin

By default, Origin of the diagram page will be at (0,0). A virtual method `AdjustPageOrigin` of PageSettings class is used to customize the origin of the page based on page size (`PageWidth` and `PageHeight`) and diagram elements position which in turn help to reduce the number of pages being printed.

`AdjustPageOrigin` method is having `Info` property in its argument. And it is having following properties and methods,

| Properties/Methods | Description | Output |
|---|---|---|
| Truncate | To customize the origin based on the page size | ![Truncate](Page-Settings_images/Truncate.gif) |
| Trim | To customize the origin based on the pixel. Page origin will be position of the most top left element | ![Trim](Page-Settings_images/Trim.gif) |
| RowCount | To get the number of pages available in row-wise manner. | ![RowCount](Page-Settings_images/RowCount.PNG) |
| ColumnCount | To get the number of pages available in column-wise manner.| ![ColumnCount](Page-Settings_images/ColumnCount.png) |
| PageOrigin | To get the origin of the page | ![PageOrigin](Page-Settings_images/PageOrigin.png)  |

{% tabs %}
{% highlight C# %}

//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//create instance for PageCustomClass using PageSettings
diagram.PageSettings = new CustomPageSettings();

//Create a custom class which is derived form page setting class
public class CustomPageSettings : PageSettings
{
  public override void AdjustPageOrigin()
  {
    //Specifies the row count
    double rowCount = Info.RowCount;
    //Specifies the column count
    double columnCount = Info.ColumnCount;
    //Specifies the page origin
    Point pageOrigin = Info.PageOrigin;

    Info.Truncate();
  }
}
    
{% endhighlight %}
{% endtabs %}

N> This customization will play role in reducing the number of pages in printing.

{% seealso %}

[How to add or remove grid lines for diagram page](/wpf/sfdiagram/gridlines)

[How to define scroll setting for diagram page](/wpf/sfdiagram/scroll-settings)

[How to add rulers for diagram page](/wpf/sfdiagram/rulers)

[How to print the diagram pages](/wpf/sfdiagram/printing)

[How to export the diagram page](/wpf/sfdiagram/exporting)

[How to interact with diagram page ](/wpf/sfdiagram/interaction)

{% endseealso %}