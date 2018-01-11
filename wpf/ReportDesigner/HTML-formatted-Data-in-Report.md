---
layout: post
title: HTML formatted data in Reports | ReportDesigner | wpf | Syncfusion
description: HTML formatted data
platform: wpf
control: Report Designer
documentation: ug
---

## HTML Formatted Data with Report

Text box can be used to show HTML formatted data with report viewer that retrieved from data source. HTML text can be in form of simple or complex expressions. We have to create the placeholder in textbox and show the HTML formatted data from dataset. The following steps are used to import HTML text in report.

1.	Draw a textbox report item. Right click on the text box and select “Create Placeholder”.

![](HTML-formatted-Data-in-Report_images/textbox_image.png)

2.	Select the markup type as “HTML – Interpret HTML tags as styles” from “Placeholder Properties” dialog box.

![](HTML-formatted-Data-in-Report_images/placeholder_propety_dialog.png)

3.	Now, select the dataset field which contains HTML text or you can provide HTML text as expression.

![](HTML-formatted-Data-in-Report_images/HTML_fomatted_data.png)

4.	Then Click OK. HTML formatted data will show as below in report designer preview and report viewer.

![](HTML-formatted-Data-in-Report_images/HTML_Formatted_Data_Output.png)

## Supported HTML Tags

* Hyperlinks: `<A HREF>`
* Fonts: `<FONT>`
* Header, style and block elements: `<H{n}>, <DIV>, <SPAN>, <P>, <DIV>, <LI>, <HN>`
* Text format: `<B>, <I>, <U>, <S>`

## Limitations of Cascading Style Sheet Attributes

The following is a list of attributes that are supported:

* text-align, text-indent
* font-family
* font-size
* Only valid RDL size values, in absolute CSS length units are supported. Supported units are: in, cm, mm, pt, pc, px, ex, em.
* Relative CSS length units are ignored and not supported. Unsupported units include percentage (%), rem.
* color
* padding, padding-bottom, padding-top, padding-right, padding-left
* font-weight
