---
title: How to paste WordDocument from DocIO in the WPF SfRichTextBoxAdv. | Syncfusion
description: Learn here all about how to paste WordDocument from DocIO in Syncfusion WPF SfRichTextBoxAdv and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: paste-WordDocument-from-DocIO
---

# Paste WordDocument from DocIO in the WPF SfRichTextBoxAdv

The PasteCommand with [WordDocument](https://help.syncfusion.com/file-formats/docio/getting-started) as a parameter is a feature that allows you to paste the contents of a WordDocument into the current selection of the SfRichTextBoxAdv control. This feature enables you to insert another DOCX file, HTML, and part of the content from another document, such as images, formatted text, and more, into the SfRichTextBoxAdv from a WordDocument instance. This provides a convenient and efficient way to transfer and display complex document structures from Word documents directly within the SfRichTextBoxAdv.

The following code example illustrates how to design a table using WordDocument and paste it into the SfRichTextBoxAdv.

{% tabs %}
{% highlight c# %}
///Creates an instance of WordDocument class 
  WordDocument document = new WordDocument();
///Adds a section into Word document
  IWSection section = document.AddSection();
///Adds a new table into Word document
  IWTable table = section.AddTable();
///Specifies the total number of rows & columns
  table.ResetCells(10, 6);
///Iterates the rows of the table
for (int i = 0; i < table.Rows.Count; i++)
{
    WTableRow wTableRow = table.Rows[i];
    ///Iterates through the cells of rows
    for (int j = 0; j < wTableRow.Cells.Count; j++)
    {
            WTableCell wTableCell = wTableRow.Cells[j];
            ///Specifies the left, right, top and bottom padding of the cell.
            wTableCell.CellFormat.Paddings.Left = 7.5f;
            wTableCell.CellFormat.Paddings.Top = 7.5f;
            wTableCell.CellFormat.Paddings.Right = 7.5f;
            wTableCell.CellFormat.Paddings.Bottom = 7.5f;
            ///set background color for cell.
            wTableCell.CellFormat.BackColor = Color.Blue;
            ///Set border type for tablecell borders
            wTableCell.CellFormat.Borders.BorderType = BorderStyle.Single;
            ///Set color for tablecell borders
            wTableCell.CellFormat.Borders.Color = Color.Red;
            wTableCell.CellFormat.Borders.Top.Color = Color.Red;
            wTableCell.CellFormat.Borders.Bottom.Color = Color.Red;
            wTableCell.CellFormat.Borders.Right.Color = Color.Red;
            wTableCell.CellFormat.Borders.Left.Color = Color.Red;
            ///Set line width for tablecell borders.
            wTableCell.CellFormat.Borders.LineWidth = 7.5f;
    }
}
///Paste the WordDocument into SfRichTextBoxAdv.
SfRichTextBoxAdv.PasteCommand.Execute(document,richTextBoxAdv);
{% endhighlight %}
{% endtabs %}

# Limitation
When the document content is pasted into the SfRichTextBoxAdv control using WordDocument as the parameter, the history will not be maintained. That is, if a table is created using WordDocument, with multiple formats applied, and the table is pasted into the SfRichTextBoxAdv control, performing Undo will remove the inserted table, and performing Redo will insert the table again.