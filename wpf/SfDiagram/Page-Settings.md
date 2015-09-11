---
layout: post
title: Page-Settings
description: page settings
platform: wpf
control: Control Name undefined
documentation: ug
---

### Page Settings

Description

Page settings enable users to customize the appearance, width, height, and measurement units of the diagram page. Page size will be based on any one of the following options:

* Content of the page.
* Specified PageWidth and PageHeight.
* Both the content of the page and the specified PageWidth and PageHeight values.





Page Appearance Based on Content of the Page

If the PageWidth and PageHeight are not specified, the page size will be updated based on the content of the page.



By default, the page size will be updated based on the content.



![](Page-Settings_images/Page-Settings_img1.png)
{:.image }


_Figure_ _90__: Content-based Page Size_



Page Appearance Based on PageWidth and PageHeight

If PageWidth and PageHeight are specified and MultiplePage is set to false, the page size will be the specified values.



Set PageWidth and PageHeight



[C#]

//Initializing SfDiagram

SfDiagram diagramControl = new SfDiagram();

diagramControl.PageSettings.PageWidth = 500;

diagramControl.PageSettings.PageHeight = 500;









![](Page-Settings_images/Page-Settings_img2.png)
{:.image }




_Figure_ _91__: Single Page with Specified Width and Height_



MultiplePage and PageBreaks

If MultiplePage is set to true, based on the content of the page, the page size will be in multiples of the specified PageWidth and PageHeight. If ShowPageBreaks is set to true, page break lines will be rendered to separate the pages.



Set MultiplePage

[C#]

//Initializing SfDiagram

SfDiagram diagramControl = new SfDiagram();

diagramControl.PageSettings.PageWidth = 500;

diagramControl.PageSettings.PageHeight = 500;

diagramControl.PageSettings.MultiplePage = false;







![](Page-Settings_images/Page-Settings_img3.png)
{:.image }




_Figure_ _92__:__Multiple Pages in a Diagram_



Measurement Units

Description

An element’s position, size, and many other numeric values are measured in pixels by default. These values can be changed to standard measurement units like inches, centimeters, etc. These units can also be changed at runtime. Once the unit is changed, all numeric values will be updated to the new unit to maintain the same visual appearance. Rulers and gridlines will be updated accordingly.



To change measurement units

[C#]

//Initializing SfDiagram

SfDiagram diagramControl = new SfDiagram();

LengthUnit unit=diagramControl.PageSettings.Unit as LengthUnit;

unit.Unit = LengthUnits.Feets;







![C:/Users/Admin/Desktop/Whats New/Rulers and Units.png](Page-Settings_images/Page-Settings_img4.png)
{:.image }


_Figure_ _93__: Rulers with Different Measurement Units_

Supported Units

MeasurementUnit is an abstract class. LengthUnit is a class that implements this abstract class. LengthUnit supports following units:



* Centimeters
* Feets
* Inches
* Kilometers
* Miles
* Millileters
* Meters
* Pixels
* Yards



Custom Units

MeasurementUnit is an abstract class. The Unit property of PageSettings is of type MeasurementUnit. A new kind of measurement unit can also be created by implementing this abstract base class.

