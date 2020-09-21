---
layout: post
title: HTML formatted data in Reports | ReportDesigner | wpf | Syncfusion
description: Learn how to implement HTML formatted data in a report and import HTML text in the Syncfusion Report Designer control.
platform: wpf
control: Report Designer
documentation: ug
---

# HTML Formatted Data with Report

Text box can be used to show the HTML formatted data with the report viewer that is retrieved from the data source. HTML text can be in form of simple or complex expressions. You have to create the placeholder in textbox and show the HTML formatted data from the dataset. The following steps are used to import the HTML text in the report:

1. Draw a textbox report item. Right-click the text box and select “Create Placeholder”.
    
    ![Create Placeholder from text box](HTML-formatted-Data-in-Report_images/textbox_image.png)

2.	Select the markup type as “HTML – Interpret HTML tags as styles” from the “Placeholder Properties” dialog box.
    
    ![Select markup type as HTML](HTML-formatted-Data-in-Report_images/placeholder_propety_dialog.png)

3.	Now, select the dataset field which contains the HTML text or you can provide the HTML text as expression.
    
    ![select dataset field containing HTML text](HTML-formatted-Data-in-Report_images/HTML_fomatted_data.png)

4.	Then, click ok. The HTML formatted data will be shown as below in the report designer preview and report viewer.
    
    ![HTML formatted data shown in report designer preview](HTML-formatted-Data-in-Report_images/HTML_Formatted_Data_Output.png)

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
* Only valid RDL size values are supported in absolute CSS length units. Supported units are: in, cm, mm, pt, pc, px, ex, and em.
* Relative CSS length units are ignored and are not supported. Unsupported units include percentage (%), and rem.
* color
* padding, padding-bottom, padding-top, padding-right, and padding-left
* font-weight
