---
title: How to paste WordDocument from .NET Word library (DocIO) in the WPF SfRichTextBoxAdv. | Syncfusion
description: Learn here all about how to paste WordDocument from .NET Word library (DocIO) in Syncfusion WPF SfRichTextBoxAdv and more.
platform: WPF
control: SfRichTextBoxAdv
documentation: ug
keywords: paste-WordDocument-from-DocIO
---

# Paste WordDocument from .NET Word library (DocIO) in the WPF SfRichTextBoxAdv

The PasteCommand with [WordDocument](https://help.syncfusion.com/cr/file-formats/Syncfusion.DocIO.DLS.WordDocument.html) as a parameter is a feature that allows you to paste the contents of a WordDocument into the current selection of the SfRichTextBoxAdv control.This provides a convenient and efficient way to transfer and display complex document structures from Word documents directly within the SfRichTextBoxAdv.

Using this feature, you can achieve below things by pasting WordDocument into the SfRichTextBoxAdv at current selection:

* Perform all the document manipulation features of [.NET Word library (DocIO)](https://help.syncfusion.com/file-formats/docio/overview) and then finally insert into SfRichTextBoxAdv

* Insert another [Word document](https://help.syncfusion.com/file-formats/docio/word-file-formats) (DOC, DOCX) and [HTML](https://help.syncfusion.com/file-formats/docio/html) document from DocIO.

* Insert part of another Word document by retrieving the part of content using [bookmark functionality](https://help.syncfusion.com/file-formats/docio/working-with-bookmarks) in DocIO.

* Create new elements in scratch as per desired formatting such as [text](https://help.syncfusion.com/file-formats/docio/working-with-paragraph#working-with-text), [images](https://help.syncfusion.com/file-formats/docio/working-with-paragraph#working-with-images), [tables](https://help.syncfusion.com/file-formats/docio/working-with-tables) and more using DocIO and paste that WordDocument instance.

The following code example illustrates how to design a table with set of formatting using DocIO and paste it into the SfRichTextBoxAdv using WordDocument.

{% tabs %}
{% highlight c# %}
///Paste the WordDocument into SfRichTextBoxAdv.
WordDocument document = CreateTable();
SfRichTextBoxAdv.PasteCommand.Execute(document,richTextBoxAdv);

/// <summary>
///  The following helper method illustrates how to create table in DocIO.
/// </summary>
Private WordDocument CreateTable()
{
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
     return WordDocument
}

{% endhighlight %}
{% endtabs %}

# Limitation
When the document content is pasted into the SfRichTextBoxAdv control using WordDocument as a parameter, the history will not be maintained. That is, if a table is created using WordDocument, with multiple formats applied, and then table is pasted into the SfRichTextBoxAdv control, performing Undo will remove the inserted table, and performing Redo will insert the table again. Since, we are creating table outside of SfRichTextBoxAdv and it will not maintain history.