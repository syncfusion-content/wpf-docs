---
title: Table in WPF RichTextBox control | Syncfusion
description: Learn here all about Table support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: table
---
# Table in WPF RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv allows you to add tables into the rich text document. You can insert any rows or columns to the existing table and also can delete existing rows and columns. The SfRichTextBoxAdv also allows you to merge the selected cells into one (both vertically and horizontally).
The following code example illustrates how to add tables into the rich text document.

{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:DocumentAdv>
    <RichTextBoxAdv:SectionAdv>
        <RichTextBoxAdv:TableAdv>
            <RichTextBoxAdv:TableRowAdv>
                <RichTextBoxAdv:TableCellAdv>
                    <RichTextBoxAdv:TableCellAdv.CellFormat>
                        <RichTextBoxAdv:CellFormat CellWidth="240"/>
                    </RichTextBoxAdv:TableCellAdv.CellFormat>
                    <RichTextBoxAdv:ParagraphAdv>
                        <RichTextBoxAdv:SpanAdv>Cell 1</RichTextBoxAdv:SpanAdv>
                    </RichTextBoxAdv:ParagraphAdv>
                </RichTextBoxAdv:TableCellAdv>
                <RichTextBoxAdv:TableCellAdv>
                    <RichTextBoxAdv:TableCellAdv.CellFormat>
                        <RichTextBoxAdv:CellFormat CellWidth="240"/>
                    </RichTextBoxAdv:TableCellAdv.CellFormat>
                    <RichTextBoxAdv:ParagraphAdv>
                        <RichTextBoxAdv:SpanAdv>Cell 2</RichTextBoxAdv:SpanAdv>
                    </RichTextBoxAdv:ParagraphAdv>
                </RichTextBoxAdv:TableCellAdv>
            </RichTextBoxAdv:TableRowAdv>
        </RichTextBoxAdv:TableAdv>
        <RichTextBoxAdv:ParagraphAdv/>
    </RichTextBoxAdv:SectionAdv>
</RichTextBoxAdv:DocumentAdv>

{% endhighlight %}
{% highlight c# %}
// Initializes a document.
DocumentAdv document = new DocumentAdv();

// Initialize a section.
SectionAdv section = new SectionAdv();

// Initialize a table.
TableAdv tableAdv = new TableAdv();

// Initialize a row.
TableRowAdv tableRowAdv = new TableRowAdv();

// Initialize a table cell.
TableCellAdv tableCellAdv = new TableCellAdv();
tableCellAdv.CellFormat.CellWidth = 240;

// Initializes a paragraph.
ParagraphAdv paragraphAdv = new ParagraphAdv();
SpanAdv spanAdv = new SpanAdv();
spanAdv.Text = "Cell 1";
paragraphAdv.Inlines.Add(spanAdv);

tableCellAdv.Blocks.Add(paragraphAdv);
// Initialize and add any number of blocks to the cell here.

tableRowAdv.Cells.Add(tableCellAdv);
// Initialize and add any number of cells to the row here.

tableAdv.Rows.Add(tableRowAdv);
// Initialize and add any number of rows to the table here.

section.Blocks.Add(tableAdv);
// Initialize and add any number of blocks to the section here.

document.Sections.Add(section);
// Initialize and add any number of sections to the document here.

// Assign the documen to the RichTextBoxAdv instance.
richTextBoxAdv.Document = document;


{% endhighlight %}
{% highlight VB %}
' Initializes a document.
Dim document As New DocumentAdv()

' Initialize a section.
Dim section As New SectionAdv()

' Initialize a table.
Dim tableAdv As New TableAdv()

' Initialize a row.
Dim tableRowAdv As New TableRowAdv()

' Initialize a table cell.
Dim tableCellAdv As New TableCellAdv()
tableCellAdv.CellFormat.CellWidth = 240

' Initializes a paragraph.
Dim paragraphAdv As New ParagraphAdv()
Dim spanAdv As New SpanAdv()
spanAdv.Text = "Cell 1"
paragraphAdv.Inlines.Add(spanAdv)

tableCellAdv.Blocks.Add(paragraphAdv)
' Initialize and add any number of blocks to the cell here.

tableRowAdv.Cells.Add(tableCellAdv)
' Initialize and add any number of cells to the row here.

tableAdv.Rows.Add(tableRowAdv)
' Initialize and add any number of rows to the table here.

section.Blocks.Add(tableAdv)
' Initialize and add any number of blocks to the section here.

document.Sections.Add(section)
' Initialize and add any number of sections to the document here.

' Assign the documen to the RichTextBoxAdv instance.
richTextBoxAdv.Document = document


{% endhighlight %}
{% endtabs %}

## UI Commands for accessing table

The following code example illustrates how to bind the Button UI Command for inserting a table.
{% tabs %}
{% highlight xaml %}
<!-- Inserts the table with default size of one row and two columns -->
<Button Content="Insert Table" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertTableCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />

<!-- Inserts the table with the size of two rows and three columns -->
<Button Content="Insert Table" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertTableCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" CommandParameter="2,3"/>


{% endhighlight %}
{% highlight c# %}
// InsertTableCommand accepting string parameter.
SfRichTextBoxAdv.InsertTableCommand.Execute("2,3", richTextBoxAdv);

// InsertTableCommand accepting int[] with row, column size as parameter
SfRichTextBoxAdv.InsertTableCommand.Execute(new int[] { 2, 3 }, richTextBoxAdv);


{% endhighlight %}
{% highlight VB %}
' InsertTableCommand accepting string parameter.
SfRichTextBoxAdv.InsertTableCommand.Execute("2,3", richTextBoxAdv)

' InsertTableCommand accepting int[] with row, column size as parameter
SfRichTextBoxAdv.InsertTableCommand.Execute(New Integer() {2, 3}, richTextBoxAdv)


{% endhighlight %}
{% endtabs %}


The following code example illustrates how to bind the Button UI Command for inserting rows and columns.
{% tabs %}
{% highlight xaml %}
<!-- Inserts one row above to the current row -->
<!-- Command parameter can be either Above or Below -->
<Button Content="Insert Row" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertRowCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" CommandParameter="Above"/>
<!-- Inserts one column to the right of current column -->
<!-- Command parameter can be either Left or Right -->
<Button Content="Insert Column" Command="RichTextBoxAdv:SfRichTextBoxAdv.InsertColumnCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" CommandParameter="Right"/>


{% endhighlight %}

{% endtabs %}

The following code example illustrates how to bind the Button UI Command for selecting cell, row, column and table.
{% tabs %}
{% highlight xml %}
<!--Selects the Cell--> 
<Button Content="Select Cell" Command="RichTextBoxAdv:SfRichTextBoxAdv.SelectCellCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!--Selects the Column-->
<Button Content="Select Column" Command="RichTextBoxAdv:SfRichTextBoxAdv.SelectColumnCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!--Selects the Row-->
<Button Content="Select Row" Command="RichTextBoxAdv:SfRichTextBoxAdv.SelectRowCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!--Selects the Table-->
<Button Content="Select Table" Command="RichTextBoxAdv:SfRichTextBoxAdv.SelectTableCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />

{% endhighlight %}

{% endtabs %}

The following code example illustrates how to bind the Button UI Command for merging selected cells.
{% tabs %}
{% highlight xaml %}
<!-- Merges the selected cells -->
<Button Content="Merge Cells" Command="RichTextBoxAdv:SfRichTextBoxAdv.MergeSelectedCellsCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}

The following code example illustrates how to bind the Button UI Command to change content alignment of the selected cells.
{% tabs %}
{% highlight xaml %}
<!--Change cell content alignment with command parameter as comma separated(vertical alignment and text alignment)-->
<Button Content="Cell Content Alignment" Command="RichTextBoxAdv:SfRichTextBoxAdv.CellContentAlignmentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" CommandParameter="Top,Left" />

<!--or-->

<!--Change cell content alignment with command parameter single sting (vertical alignment and text alignment)-->
<Button Content="Cell Content Alignment" Command="RichTextBoxAdv:SfRichTextBoxAdv.CellContentAlignmentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}"  CommandParameter="CenterRight"/>

<!--or-->

<!--Change cell content alignment with command parameter as string array(vertical alignment and text alignment string order respectively)-->
<Button Content="Cell Content Alignment" Command="RichTextBoxAdv:SfRichTextBoxAdv.CellContentAlignmentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}">
    <Button.CommandParameter>
        <x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:sys="clr-namespace:System;assembly=mscorlib">
            <sys:String>Bottom</sys:String>
            <sys:String>Left</sys:String>
        </x:Array>
    </Button.CommandParameter>
</Button>


{% endhighlight %}

{% endtabs %}

The following code example illustrates how to Button UI Command for deleting a row, deleting a column and deleting an entire table.
{% tabs %}
{% highlight xaml %}
<!-- Deletes the column -->
<Button Content="Delete Column" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteColumnCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Deletes the row -->
<Button Content="Delete Row" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteRowCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Deletes the table -->
<Button Content="Delete Table" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteTableCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}

N> You can refer to our [WPF RichTextBox](https://www.syncfusion.com/wpf-controls/richtextbox) feature tour page for its groundbreaking feature representations.You can also explore our [WPF RichTextBox example](https://github.com/syncfusion/wpf-demos/tree/master/richtextbox) to knows how to render and configure the editing tools.