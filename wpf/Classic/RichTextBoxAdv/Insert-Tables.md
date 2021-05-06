---
layout: post
title: Insert-Tables in WPF Wizard Control control | Syncfusion
description: Learn here all about Insert-Tables support in Syncfusion WPF RichTextBoxAdv (Classic) control and more.
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

# Insert-Tables in WPF RichTextBoxAdv (Classic)

Table support for the RichTextBoxAdv control has been implemented as in Microsoft Word. This is used to insert tables with user-defined rows and columns, and it also allows the user to insert multiple tables for every cell.


{% tabs %}
{% highlight xaml %}

              
<syncfusion:TableAdv>                          
<syncfusion:TableRowAdv>                             
<syncfusion:TableCellAdv>                                 
 <syncfusion:ParagraphAdv>                                      
<syncfusion:SpanAdv Text="Table support"/>                                 
</syncfusion:ParagraphAdv>                              
</syncfusion:TableCellAdv>                        
 </syncfusion:TableRowAdv>                      
</syncfusion:TableAdv>
{% endhighlight %}

{% highlight C# %}


TableAdv table = new TableAdv();          
TableRowAdv row = new TableRowAdv();          
TableCellAdv cell = new TableCellAdv();         
ParagraphAdv paragraph = new ParagraphAdv();         
 SpanAdv span = new SpanAdv();          
 span.Text = "Table support";          
 paragraph.Inlines.Add(span);          
 cell.Blocks.Add(paragraph);          
 row.Cells.Add(cell);          
 table.Rows.Add(row);

{% endhighlight %}
{% endtabs %}

## Editing Support

Editing is done in the table cell. Table width and height will be calculated for every change in the block of cells. We can insert an image, hyperlink, and UIElement in the table cells.

## Selection Support

The table, table cells, table rows, and table columns have separate selection behavior to select the corresponding element in the blocks. Table cell selection can be achieved by double-clicking when inside the table cells. Table row and table column selection can be achieved by the SelectRow, SelectCell, and SelectTable commands.

## Insert n*n Tables

We can insert n*n tables inside a single table cell. It can be achieved by InsertTable.

## Insert n*n Columns

We can insert n* n columns in a table. It can be achieved by the InsertColumn command. This is possible only when a number of cells or the current position inside the table is selected.

## Insert n*n Rows

We can insert n* n rows in a table. It can be achieved by the InsertRow command. This is possible only when a number of cells or the current position inside the table is selected.

## Delete Table

We can delete the table from the document. It can be achieved by the DeleteTable command. This is possible only when a number cells or the current position inside the table is selected.

## Delete n*n Rows

We can delete n*n rows at a single attempt. It can be achieved by the DeleteRow command. This is possible only when a number of cells or the current position inside the table is selected.

## Delete n*n Columns

We can delete n*n columns at a single attempt. It can be achieved by the DeleteColumn command. This is possible only when a number of cells or the current position inside the table is selected.

## Merging

The user can merge the n*n cells into a single cell. It can be achieved by the MergeSelectedCells command. This is possible only when a number of cells are selected. The RowSpan and ColumnSpan properties in the table cell take responsibility for this.

