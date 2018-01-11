---
layout: post
title: HTML formatted data in Reports | ReportViewer | WPF | Syncfusion
description: HTML formatted data in Reports
platform: wpf
control: ReportViewer
documentation: ug
---

## HTML Formatted Data with Report

Report Viewer supports to show the HTML formatted data with Textbox report items along with inline CSS. This section will provide the information of supported tags and limitations.

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