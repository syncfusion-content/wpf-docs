---
title: Essential Studio for WPF 2018 volume 1 Migration document
description: Learn about Easy Customization support in Syncfusion WPF Release notes control, its elements, and more.
platform: wpf
documentation: ug
keywords: migration, upgrade-changes, 2018vol1-changes
---
# SfRichTextBoxAdv in WPF Release notes

The SfRichTextBoxAdv control validates DocumentAdv instance internally when the value of Document property is updated. It ensures that minimal child elements are available in each container elements like,

* At least one section should be available in document

* At least one paragraph should be available in each table cell, section body, header and footer

* At least one row should be available in each table

* At least one cell should be available in each table row

* At least one paragraph should be available after a table 

N> In earlier versions, this internal validation to ensure minimal child element is not performed.

The following code example demonstrates how to create a document with a section, a table and a paragraph from scratch using v15.4.0.20 and earlier versions.
{% tabs %}
{% highlight c# %}
// Creates new instance of SfRichTextBoxAdv control.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();

// Creates a new document.
richTextBoxAdv.Document = new DocumentAdv();

// Creates a new section and add it to the document.
SectionAdv section = new SectionAdv();
richTextBoxAdv.Document.Sections.Add(section);

// Creates a 1 x 1 table.
TableAdv table = new TableAdv();
TableRowAdv row = new TableRowAdv();
TableCellAdv cell = new TableCellAdv();
cell.Blocks.Add(new ParagraphAdv());

// Adds the table to the section.
section.Blocks.Add(new TableAdv());

// Adds a paragraph the section.
section.Blocks.Add(new ParagraphAdv());

{% endhighlight %}

{% endtabs %}

The following code example demonstrates how to create a document with a section, a table and a paragraph from scratch using v16.1.0.24 and later versions.
{% tabs %}
{% highlight c# %}
// Creates new instance of SfRichTextBoxAdv control.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();

// Creates a new document.
richTextBoxAdv.Document = new DocumentAdv();
// A section with an empty paragraph will be added internally to ensure minimal child elements.

// Adds a 1 x 1 table to the section.
richTextBoxAdv.Document.Sections[0].Blocks.Insert(0, new TableAdv());

{% endhighlight %}

{% endtabs %}
