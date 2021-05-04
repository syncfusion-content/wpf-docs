---
layout: post
title: Links in WPF Wizard Control control | Syncfusion
description: Learn here all about Links support in Syncfusion WPF SpreadsheetControl (Classic) control and more.
platform: wpf
control: Spreadsheet
documentation: ug
---

# Links in WPF SpreadsheetControl (Classic)

## Bookmarks and Hyperlinks

A hyperlink is a convenient way to navigate from one workbook to another workbook. Links created in the native Excel will be imported to the Spreadsheet Control. You can also add new links.

### Adding hyperlink to Cell

You can add the hyperlink to the spreadsheet cell using the Insert Hyperlink dialog box. You can open the Insert Hyperlink dialog using the HyperlinkCommand.

![Links_img1](Links_images/Links_img1.png)

The following code illustrates how to bind the HyperlinkCommand__a button: 

{% highlight xaml %}

<Button Command="{Binding Path= HyperlinkCommand}">

</Button>

{% endhighlight %}
