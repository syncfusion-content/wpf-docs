---
layout: post
title: HTML formatted data in Reports | ReportViewer | WPF | Syncfusion
description: HTML formatted data in Reports
platform: wpf
control: ReportViewer
 documentation: ug
---

## HTML Formatted Data with Report

Report viewer supports showing the HTML formatted data with Textbox report items along with the inline CSS. This section provides the information about supported tags and limitations.

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