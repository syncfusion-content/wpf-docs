---
title: Table
description: table
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: table
---
# Table

The SfRichTextBoxAdv allows you to add tables into the rich text document. You can insert any rows or columns to the existing table and also can delete existing rows and columns. The SfRichTextBoxAdv also allows you to merge the selected cells into one (both vertically and horizontally).
The following code example illustrates how to add tables into the rich text document.
<table>
<tr>
<td colspan=1 rowspan=1>
<RichTextBoxAdv:DocumentAdv><br/><RichTextBoxAdv:SectionAdv><br/><RichTextBoxAdv:TableAdv><br/><RichTextBoxAdv:TableRowAdv><br/><RichTextBoxAdv:TableCellAdv><br/><RichTextBoxAdv:TableCellAdv.CellFormat><br/><RichTextBoxAdv:CellFormat CellWidth="240"/><br/></RichTextBoxAdv:TableCellAdv.CellFormat><br/><RichTextBoxAdv:ParagraphAdv><br/><RichTextBoxAdv:SpanAdv>Cell 1</RichTextBoxAdv:SpanAdv><br/></RichTextBoxAdv:ParagraphAdv><br/></RichTextBoxAdv:TableCellAdv><br/><RichTextBoxAdv:TableCellAdv><br/><RichTextBoxAdv:TableCellAdv.CellFormat><br/><RichTextBoxAdv:CellFormat CellWidth="240"/><br/></RichTextBoxAdv:TableCellAdv.CellFormat><br/><RichTextBoxAdv:ParagraphAdv><br/><RichTextBoxAdv:SpanAdv>Cell 2</RichTextBoxAdv:SpanAdv><br/></RichTextBoxAdv:ParagraphAdv><br/></RichTextBoxAdv:TableCellAdv><br/></RichTextBoxAdv:TableRowAdv><br/></RichTextBoxAdv:TableAdv><br/><RichTextBoxAdv:ParagraphAdv/><br/></RichTextBoxAdv:SectionAdv><br/></RichTextBoxAdv:DocumentAdv><br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
// Initializes a document.<br/>DocumentAdv document = new DocumentAdv();<br/>// Initialize a section.<br/>SectionAdv section = new SectionAdv();<br/>// Initialize a table.<br/>TableAdv tableAdv = new TableAdv();<br/>// Initialize a row.<br/>TableRowAdv tableRowAdv = new TableRowAdv();<br/>// Initialize a table cell.<br/>TableCellAdv tableCellAdv = new TableCellAdv();<br/>tableCellAdv.CellFormat.CellWidth = 240;<br/>// Initializes a paragraph.<br/>ParagraphAdv paragraphAdv = new ParagraphAdv();<br/>SpanAdv spanAdv = new SpanAdv();<br/>spanAdv.Text = "Cell 1";<br/>paragraphAdv.Inlines.Add(spanAdv);<br/>tableCellAdv.Blocks.Add(paragraphAdv);<br/>// Initialize and add any number of blocks to the cell here.<br/>tableRowAdv.Cells.Add(tableCellAdv);<br/>// Initialize and add any number of cells to the row here.<br/>tableAdv.Rows.Add(tableRowAdv);<br/>// Initialize and add any number of rows to the table here.<br/>section.Blocks.Add(tableAdv);<br/>// Initialize and add any number of blocks to the section here.<br/>document.Sections.Add(section);<br/>// Initialize and add any number of sections to the document here.<br/>// Assign the documen to the RichTextBoxAdv instance.<br/>richTextBoxAdv.Document = document;<br/></td></tr>
</table>
## UI Commands for accessing table

The following code example illustrates how to bind the Button UI Command for inserting a table.
<table>
<tr>
<td colspan=1 rowspan=1>
<!-- Inserts the table with default size of one row and two columns --><br/><Button Content="Insert Table" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertTableCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" /><br/><!-- Inserts the table with the size of two rows and three columns --><br/><Button Content="Insert Table" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertTableCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" CommandParameter="2,3"/><br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
// InsertTableCommand accepting string parameter.<br/>SfRichTextBoxAdv.InsertTableCommand.Execute("2,3", richTextBoxAdv);<br/>// InsertTableCommand accepting int[] with row, column size as parameter<br/>SfRichTextBoxAdv.InsertTableCommand.Execute(new int[] { 2, 3 }, richTextBoxAdv);<br/></td></tr>
</table>
The following code example illustrates how to bind the Button UI Command for inserting rows and columns.
{% tabs %}
{% highlight xml %}
<!-- Inserts one row above to the current row -->
<!-- Command parameter can be either Above or Below -->
<Button Content="Insert Row" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertRowCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" CommandParameter="Above"/>
<!-- Inserts one column to the right of current column -->
<!-- Command parameter can be either Left or Right -->
<Button Content="Insert Column" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertColumnCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" CommandParameter="Right"/>


{% endhighlight %}

The following code example illustrates how to Button UI Command for deleting a row, deleting a column and deleting an entire table.
{% highlight xml %}
<!-- Deletes the column -->
<Button Content="Delete Column" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteColumnCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Deletes the row -->
<Button Content="Delete Row" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteRowCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Deletes the table -->
<Button Content="Delete Table" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteTableCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

The following code example illustrates how to bind the Button UI Command for merging selected cells.
{% highlight xml %}
<!-- Merges the selected cells -->
<Button Content="Merge Cells" Command="RichTextBoxAdv:SfRichTextBoxAdv.MergeSelectedCellsCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}
