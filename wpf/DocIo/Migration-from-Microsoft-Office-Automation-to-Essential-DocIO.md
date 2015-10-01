---
layout: post
title: Migration-from-Microsoft-Office-Automation-to-Essential-DocIO
description: migration from microsoft office automation to essential docio
platform: wpf
control: DocIO
documentation: ug
---

# Migration from Microsoft Office Automation to Essential DocIO

## Mail Merge

The Mail Merge feature can be used to generate reports and letters in MS Word. The following code examples show how to generate an employee report from an MDB data source using Office Automation and DocIO.

### Using MS Office Interop

Office Automation performs the Mail Merge by executing a SQL query on the Word document. The output of the Mail Merge can be sent to a new Word document. Alternatively, it can be sent to a printer, a fax machine, or forwarded to an e-mail address.


{% tabs %}
{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;---------
//Initializes objects.
instance nullobject = Missing.Value;
instance filepath = "EmployeesReportDemo.doc";
instance sqlStmt = "SELECT * FROM [Employees]";
string sDBPath = "Northwind.mdb";
//Starts the Word application.
word.Application wordApp = new word.Application();
//Opens the Word document.
word.Document document = wordApp.Documents.Open(ref filepath, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject);
wordApp.Visible = false;
//Performs Mail Merge.   
  document.MailMerge.OpenDataSource(sDBPath, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref sqlStmt,ref nullobject, ref nullobject, ref nullobject);document.MailMerge.Execute(ref nullobject);
//Sends output of Mail Merge to a new document.
document.MailMerge.Destination = word.WdMailMergeDestination.wdSendToNewDocument;
//Closes the document.document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports Word = Microsoft.Office.Interop.Word----------------
'Initializes objects.
Dim nullobject As Object = Missing.Value
Dim dataBase As String = "Northwind.mdb"
Dim filePath As Object = "EmployeesReportDemo.doc"
Dim sqlStmt As String = "SELECT * FROM [Employees]"
Dim falseobj As Object = False
'Starts the Word application.
Dim wordApp As word.Application = New word.Application()
'Opens the Word document.
Dim doc As word.Document = wordApp.Documents.Open(filePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, falseobj, nullobject, nullobject, nullobject, nullobject) wordApp.Visible = False'Performs Mail Merge.With doc.MailMerge.OpenDataSource(dataBase, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, sqlStmt, nullobject, nullobject, nullobject).Execute(nullobject).Destination = word.WdMailMergeDestination.wdSendToNewDocumentEnd With
'Closes the document.
doc.Close(nullobject, nullobject, nullobject)'Quits the application.wordApp.Quit(nullobject, nullobject, nullobject)
{% endhighlight   %}
{% endtabs %}


### Using DocIO

DocIO performs Mail Merge using the following methods:

* Execute
* ExecuteGroup
* ExecuteNestedGroup

The following code example performs Mail Merge using the Execute method.


{% tabs %}
{% highlight c#  %}
string dataBase = "Northwind.mdb";
//Opens existing template.
WordDocument doc = new WordDocument("EmployeesReportDemo.doc", FormatType.Doc);
//Gets Data from the Database.
OleDbConnection conn = newOleDbConnection("Provider=Microsoft.Jet.OLEDB.4.0;
Data Source=" + dataBase);conn.Open();
//Populates the data table.DataTable table = new DataTable();
OleDbDataAdapter adapter = new OleDbDataAdapter("select * from employees", conn);
adapter.Fill(table);
adapter.Dispose();
//Performs Mail Merge.
doc.MailMerge.Execute(table);
//Saves the document.
doc.Save("MailMerge.doc", FormatType.Doc);
//Closes the document.doc.Close();
{% endhighlight   %}
{% highlight vbnet %}
Dim dataBase As String = "Northwind.mdb"‘Opens the Word document.
Dim doc As WordDocument = New WordDocument("EmployeesReportDemo.doc")
‘Creates database connection.
Dim conn As OleDbConnection = New OleDbConnection("Provider=Microsoft.Jet.OLEDB.4.0;Data Source=" + dataBase)conn.Open()
‘Populates data table.
Dim table As DataTable = New DataTable()
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter("select * from employees", conn)adapter.Fill(table)adapter.Dispose()
‘Performs Mail Merge.
doc.MailMerge.Execute(table)
‘Saves the document.
doc.Save("MailMerge.doc", FormatType.Doc)
‘Closes the document.
doc.Close()
{% endhighlight   %}
{% endtabs %}


N> For more information on mail merge using DocIO, you can refer to online documentation link: <http://docs.syncfusion.com/windowsforms/docio/mail-merge#mail-merge-1>
 

### Find and Replace

This section illustrates how to perform a simple Find and replace operation in a Word document using MS Office Interop and DocIO.

Using MS Office Interop

The following code example shows you how to search for a word in a Word document, replace it with another word and save the document under a new name.



{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = Missing.Value;
instance filepath = "FindAndReplaceTemplate.doc";
instance newFilePath = "FindAndReplace.doc";
instance item = word.WdGoToItem.wdGoToPage;
instance whichItem = word.WdGoToDirection.wdGoToFirst;
instance replaceAll = word.WdReplace.wdReplaceAll;
instance forward = true;instance matchAllWord = true;
instance matchCase = false;instance originalText = "Hello";
instance replaceText = "World";instance save = true;
//Starts the Word application.
word.Application wordApp = new word.Application();
//Opens the Word document.
word.Document document = wordApp.Documents.Open(ref filepath, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject);wordApp.Visible = false;
//Searches and replaces text.
document.GoTo(ref item, ref whichItem, ref nullobject, ref nullobject);
foreach (word.Range rng in document.StoryRanges){rng.Find.Execute(ref originalText, ref matchCase, ref matchAllWord, refnullobject, ref nullobject, ref nullobject, ref forward, ref nullobject, refnullobject, ref replaceText, ref replaceAll, ref nullobject, ref nullobject,ref nullobject, ref nullobject);}
//Saves the document.
document.SaveAs(ref newFilePath, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject);
 //Closes the document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);   
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word
----------------‘Initializes objects.
Dim nullobject As Object = Missing.Value
Dim filePath As Object = "FindAndReplaceTemplate.doc"
Dim newFilePath As Object = "FindAndReplace.doc"
Dim item As Object = word.WdGoToItem.wdGoToPage
Dim whichItem As Object = word.WdGoToDirection.wdGoToFirst
Dim replaceAll As Object = word.WdReplace.wdReplaceAll
Dim forward As Object = TrueDim matchAllWord As Object = True
Dim matchCase As Object = FalseDim originalText As Object = "Hello"
Dim replaceText As Object = "World"
Dim save As Object = True
Dim falseObj As Object = False‘Starts the Word application.
Dim wordApp As word.Application = New word.Application()
‘Opens the Word document.
Dim doc As word.Document = wordApp.Documents.Open(filePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, falseobj, nullobject, nullobject, nullobject, nullobject)wordApp.Visible = False‘Searches and replaces text.doc.GoTo(item, whichItem, nullobject, nullobject)
For Each rng As word.Range In doc.StoryRangesrng.Find.Execute(originalText, matchCase, matchAllWord, nullobject, nullobject, nullobject, forward, nullobject, nullobject, replaceText, replaceAll, nullobject, nullobject, nullobject, nullobject)Next
‘Saves the document.
doc.SaveAs(newFilePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)
‘Closes the document.
doc.Close(nullobject, nullobject, nullobject)‘Quits the application.
wordApp.Quit(nullobject, nullobject, nullobject)
{% endhighlight   %}


### Using DocIO

The following code example shows you how to perform a simple “Find and Replace” operation using DocIO.


{% tabs %}
{% highlight c#  %}
//Opens the Word document.
WordDocument doc = new WordDocument("FindAndReplaceTemplate.doc",FormatType.Doc);
//Defines replacement text.
string replaceText = "World";
//Performs replace.
doc.Replace(new Regex("Hello"), replaceText);
//Saves the document.
doc.Save("Find And Replace.doc");
//Closes the document.doc.Close();
{% endhighlight   %}
{% highlight vbnet  %}
‘Opens the Word document.
Dim doc As WordDocument = New WordDocument("FindAndReplaceTemplate.doc")
‘Defines text to be replaced.
Dim replaceText As String = "World"
‘Performs replace.doc.Replace(New Regex("Hello"), replaceText)
‘Saves the document.
doc.Save("Find And Replace.doc")
‘Closes the document.doc.Close()
{% endhighlight   %}
{% endtabs %}



N> For more information on performing the find and replace operation using DocIO, you can refer to online documentation link: <http://docs.syncfusion.com/windowsforms/docio/find-and-replace>



### Bookmarks

Bookmarks identify the location of text in a Word document that you can use for future reference. For example, you might use a bookmark to identify text that you want to revise later. Instead of scrolling through the document to locate the text, you can identify the text location by using the Bookmark dialog box.

### Using MS Office Interop

The following code example shows how to insert a bookmark for a range of text using Office Automation.


{% tabs %}
{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = Missing.Value;
instance newFilePath = "NewFile.doc";
 //Starts a Word application.
word.Application wordApp = new word.Application();
//Creates a new Word document.
wordApp.Documents.Add(ref nullobject, ref nullobject, ref nullobject, refnullobject);
word.Document doc = wordApp.ActiveDocument;    
//Adds a pararaph to the document.
word.Paragraph oPara1;
oPara1 = doc.Content.Paragraphs.Add(ref nullobject);
oPara1.Range.Text = "Bookmark with one word selected";
//Defines start and end positions of bookmark range.instance start = oPara1.Range.Text.IndexOf("word");
instance end = oPara1.Range.Text.LastIndexOf(" ");
instance rng = doc.Range(ref start, ref end);
//Adds bookmark.
doc.Bookmarks.Add("one_word", ref rng);
//Saves document and quits application.
doc.SaveAs(ref newFilePath, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject);
//Closes document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word
----------------‘Initializes objects.
Dim nullobject As Object = Missing.Value
Dim newFilePath As Object = "NewFile.doc"\
‘Starts a Word application.
Dim wordApp As word.Application = New word.Application()
‘Creates a new Word document.
wordApp.Documents.Add(nullobject, nullobject, nullobject, nullobject)
Dim doc As word.Document = wordApp.ActiveDocument
‘Adds a paragraph to the document.
Dim oPara As word.ParagraphoPara = doc.Content.Paragraphs.Add(nullobject)
oPara.Range.Text = "Bookmark with one word selected"
‘Defines the start and end positions of bookmark range.
Dim startobj As Object = oPara.Range.Text.IndexOf("word")
Dim endobj As Object = oPara.Range.Text.LastIndexOf(" ")
Dim rng As Object = doc.Range(startobj, endobj)
‘Adds bookmark.doc.Bookmarks.Add("one_word", rng)
‘Saves document.doc.SaveAs(newFilePath)
‘Closes document.doc.Close(nullobject, nullobject, nullobject)‘Quits application.wordApp.Quit()
{% endhighlight   %}
{% endtabs %}

### Using DocIO

The following code example shows how to insert the bookmark using DocIO. Here, the AppendBookmarkStart() and AppendBookmarkEnd() methods are used to add the bookmark.


{% tabs %}
{% highlight c#  %}
//Creates a new Word document.
WordDocument doc = new WordDocument();
IWSection section = doc.AddSection();
IWParagraph paragraph = section.AddParagraph();
paragraph.AppendText("Simple Bookmark");
paragraph = section.AddParagraph();
paragraph.AppendText("Bookmark with one ");
//Inserts bookmark.
paragraph.AppendBookmarkStart("one_word");
paragraph.AppendText("word");
paragraph.AppendBookmarkEnd("one_word");
paragraph.AppendText(" selected");
//Saves the document.
doc.Save("Bookmarks.doc");
//Closes the document.doc.Close();
{% endhighlight   %}
{% highlight vbnet   %}
‘Creates a new Word document.
Dim doc As WordDocument = New WordDocument()
Dim section As IWSection = doc.AddSection()
Dim paragraph As IWParagraph = section.AddParagraph()
paragraph.AppendText("Simple Bookmark")
paragraph = section.AddParagraph()
paragraph.AppendText("Bookmark with one ")
‘Inserts bookmark.
paragraph.AppendBookmarkStart("one_word")
paragraph.AppendText("word")
paragraph.AppendBookmarkEnd("one_word")
paragraph.AppendText(" selected")
‘Saves the document.
doc.Save("Bookmarks.doc")
‘Closes the document.
doc.Close()
{% endhighlight  %}
{% endtabs %}


N> For more information on working with bookmarks using DocIO, you can refer to the online documentation link: <http://docs.syncfusion.com/windowsforms/docio/working-with-bookmarks>

### Page Numbers

Page numbers are inserted to a Word document in the header or footer section.

### Using MS Office Interop

In the following code example, the page numbers are inserted to the footer of the Word document by adding a page number field.



{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance filepath = "NewFile.doc";
instance nullobject = Missing.Value;
//Starts the Word application.
word.Application wordApp = new word.Application();
//Opens the Word document.
word.Document document = wordApp.Documents.Open(ref filepath, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject);wordApp.Visible = false;
document.Activate();
//Seeks the page footer.
wordApp.ActiveWindow.ActivePane.View.SeekView = word.WdSeekView.wdSeekCurrentPageFooter;
//Formats the footer.
wordApp.Selection.Paragraphs.Alignment = word.WdParagraphAlignment.wdAlignParagraphCenter;
wordApp.ActiveWindow.Selection.Font.Name = "Arial";
wordApp.ActiveWindow.Selection.Font.Size = 8;   
//Adds page numbers in the footer.
Object CurrentPage = word.WdFieldType.wdFieldPage;
wordApp.ActiveWindow.Selection.Fields.Add(wordApp.Selection.Range,ref CurrentPage, ref nullobject, ref nullobject);
//Saves the document.
document.Save();
//Closes the document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word
----------------‘Initializes objects.
Dim nullobject As Object = Missing.Value
Dim filePath As Object =  "NewFile.doc"
Dim falseobj As Object = False‘Starts the application.
Dim wordApp As word.Application = New word.Application()
‘Adds a new Word document.
Dim document As word.Document = wordApp.Documents.Open(filePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, falseobj, nullobject, nullobject, nullobject, nullobject)wordApp.Visible = Falsedocument.Activate()
‘Seeks the page footer.
wordApp.ActiveWindow.ActivePane.View.SeekView = word.WdSeekView.wdSeekCurrentPageFooter
‘Formats the footer.
wordApp.Selection.Paragraphs.Alignment = word.WdParagraphAlignment.wdAlignParagraphCenterwordApp.ActiveWindow.Selection.Font.Name = "Arial"wordApp.ActiveWindow.Selection.Font.Size = 8
‘Adds page numbers in the footer.
Dim CurrentPage As Object = word.WdFieldType.wdFieldPagewordApp.ActiveWindow.Selection.Fields.Add(wordApp.Selection.Range, CurrentPage, nullobject, nullobject)
‘Saves the document.
document.Save()
‘Closes the document.
doc.Close(nullobject, nullobject, nullobject)
‘Quits application.
wordApp.Quit()
{% endhighlight   %}


### Using DocIO

DocIO provides support for adding page numbers to a Word document. The page number field can be added to the header or footer of the Word document. In the following code example, the page numbers are inserted to the footer of the Word document.


{% tabs %}
{% highlight c#  %}
//Opens the Word document.
WordDocument doc = new WordDocument("PageNumbers.docx", FormatType.Docx);
//Adds page number in the footer.
foreach (WSection sec in doc.Sections)
{  
   IWParagraph para = sec.AddParagraph();    
 para.AppendField("footer", FieldType.FieldPage);  
    para.ParagraphFormat.HorizontalAlignment = HorizontalAlignment.Center;     
 sec.PageSetup.PageNumberStyle = PageNumberStyle.Arabic;  
    sec.HeadersFooters.Footer.Paragraphs.Add(para);}
 //Saves the document.
 doc.Save("PageNumbersUpdated.docx",FormatType.Docx);
 //Closes the document.
 doc.Close();
{% endhighlight   %}
{% highlight vbnet  %}
‘Opens the Word document.
Dim doc As WordDocument = New WordDocument("PageNumbers.docx", FormatType.Docx)
‘Adds page number in the footer.
For Each sec As WSection In doc.Sections 
    Dim para As IWParagraph = sec.AddParagraph()  
   para.AppendField("footer", FieldType.FieldPage)  
   para.ParagraphFormat.HorizontalAlignment = HorizontalAlignment.Center
     sec.PageSetup.PageNumberStyle = PageNumberStyle.Arabic  
   sec.HeadersFooters.Footer.Paragraphs.Add(para)Next
‘Saves the document.doc.Save("PageNumbersUpdated.docx", FormatType.Docx)
‘Closes the document.
doc.Close()
{% endhighlight   %}
{% endtabs %}

### Document Watermark

Watermark can be a text or an image, used to mark the document as private or confidential and to write any text that gives information about the usage and credibility of the document. In Microsoft Word, you can quickly insert a watermark using the Insert Watermark command. 

### Using MS Office Interop

The following code example illustrates how to insert a text watermark as a shape using OfficeAutomation.

{% tabs %}
{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = Missing.Value;
instance newFilePath = "NewFileWatermark.doc";
//Starts the Word application.
word.Application wordApp = new word.Application();
//Creates a new Word document.
wordApp.Documents.Add(ref nullobject, ref nullobject, ref nullobject, ref nullobject);
word.Document doc = wordApp.ActiveDocument;
//Seeks the current page header.
wordApp.ActiveWindow.ActivePane.View.SeekView = word.WdSeekView.wdSeekCurrentPageHeader;
//Inserts watermark.
word.Shape watermark = wordApp.Selection.HeaderFooter.Shapes.AddTextEffect(Microsoft.Office.Core.MsoPresetTextEffect.msoTextEffect1, "Watermark", "Arial", (float)48, Microsoft.Office.Core.MsoTriState.msoTrue, Microsoft.Office.Core.MsoTriState.msoFalse, 0, 0, ref nullobject);  
  //Sets watermark properties.
watermark.Fill.Visible = Microsoft.Office.Core.MsoTriState.msoTrue;
watermark.Line.Visible = Microsoft.Office.Core.MsoTriState.msoFalse;
watermark.Fill.Solid();
watermark.Fill.ForeColor.RGB = (Int32)word.WdColor.wdColorGray30;
//Sets focus back to the document.
wordApp.ActiveWindow.ActivePane.View.SeekView = word.WdSeekView.wdSeekMainDocument;
//Saves the document.
doc.SaveAs(ref newFilePath, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject);
//Closes the document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word
----------------‘Initializes objects.
Dim nullobject As Object = Missing.Value
Dim newFilePath As Object = "NewFileWatermark.doc"
‘Starts the application.
Dim wordApp As word.Application = New word.Application()
‘Creates a new Word document.
wordApp.Documents.Add(nullobject, nullobject, nullobject, nullobject)
Dim doc As word.Document = wordApp.ActiveDocument
‘Seeks the current page header.
wordApp.ActiveWindow.ActivePane.View.SeekView = word.WdSeekView.wdSeekCurrentPageHeader
‘Adds text watermark to the document.
Dim watermark As word.Shape = wordApp.Selection.HeaderFooter.Shapes.AddTextEffect(Microsoft.Office.Core.MsoPresetTextEffect.msoTextEffect1,"Watermark", "Arial", 48, Microsoft.Office.Core.MsoTriState.msoTrue, Microsoft.Office.Core.MsoTriState.msoFalse, 0, 0, nullobject)‘Sets watermark properties.watermark.Fill.Visible = Microsoft.Office.Core.MsoTriState.msoTruewatermark.Line.Visible = Microsoft.Office.Core.MsoTriState.msoFalsewatermark.Fill.Solid()watermark.Fill.ForeColor.RGB = CType(word.WdColor.wdColorGray30, Integer)
‘Saves the document.
doc.SaveAs(newFilePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)‘Closes the document.doc.Close(nullobject, nullobject, nullobject)
‘Quits application.
wordApp.Quit()
{% endhighlight   %}
{% endtabs %}


### Using DocIO

DocIO enables you to add a text watermark and a picture watermark to a Word document. The following code example shows how to insert the picture watermark to the Word document.


{% tabs %}
{% highlight c#  %}
//Creates a new Word document.
WordDocument doc = new WordDocument();doc.EnsureMinimal();
//Adds picture watermark to the document.
PictureWatermark picWatermark = new PictureWatermark();
picWatermark.Scaling = 120f;picWatermark.Washout = true;
doc.Watermark = picWatermark;picWatermark.Picture = Image.FromFile(ImagesPath + "Water lilies.jpg");
//Saves the document.
doc.Save("Watermark.doc", FormatType.Doc);
//Closes the document.doc.Close();
{% endhighlight   %}
{% highlight vbnet  %}
‘Creates a new Word document.
Dim doc As WordDocument = New WordDocument()
doc.EnsureMinimal()‘Adds picture watermark to the document.
Dim picWatermark As PictureWatermark = New PictureWatermark()
picWatermark.Scaling = 120f
picWatermark.Washout = Truedoc.Watermark = picWatermark
picWatermark.Picture = Image.FromFile(ImagesPath and "Water lilies.jpg")
‘Saves the document.
doc.Save("Watermark.doc", FormatType.Doc)
‘Closes the document.
doc.Close()
{% endhighlight   %}
{% endtabs %}


The following code example shows how to insert the text watermark to the Word document.


{% tabs %}
{% highlight c#  %}
//Creates a new Word document.
WordDocument doc = new WordDocument();
doc.EnsureMinimal();
//Adds text watermark to the document.
TextWatermark textWatermark = new TextWatermark();
doc.Watermark = textWatermark;
textWatermark.Size = 48;
textWatermark.Layout = WatermarkLayout.Horizontal;
textWatermark.Semitransparent = false;
textWatermark.Color = Color.Black;
textWatermark.Text = "Watermark";
//Saves the document.
doc.Save("Watermark.doc", FormatType.Doc);
//Closes the document.
doc.Close();
{% endhighlight   %}
{% highlight vbnet  %}
‘Creates a new Word document.
Dim doc As WordDocument = New WordDocument()
doc.EnsureMinimal()
‘Adds text watermark to the document.
Dim TextWatermark As TextWatermark = New TextWatermark()
doc.Watermark = TextWatermarkTextWatermark.Size = 48
TextWatermark.Layout = WatermarkLayout.Horizontal
TextWatermark.Semitransparent = False
TextWatermark.Color = Color.Black
TextWatermark.Text = "Watermark"
‘Saves the document.
doc.Save("Watermark.doc", FormatType.Doc)
‘Closes the document.
doc.Close()
{% endhighlight   %}
{% endtabs %}


N> For more information on adding watermarks to a Word document using DocIO, refer to the online documentation link: 
<http://docs.syncfusion.com/windowsforms/docio/working-with-word-documents#working-with-watermarks>

### Header or Footer

Headers and footers are displayed at the top and bottom of the document pages respectively. The headers and footers can be inserted with text, graphics, and nearly any other information that is contained in the document. 

### Using MS Office Interop 

The following code example illustrates how to add headers and footers to a Word document. In this example, page numbers are inserted to the header and a text is inserted to the footer.


{% tabs %}
{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = Missing.Value;
instance filePath = GetPath("original.doc");
instance newFilePath = GetPath("HeaderFooterOffice.doc");
//Starts the Word application.
word.Application wordApp = new word.Application();
//Opens the Word document.
word.Document document = wordApp.Documents.Open(ref filePath, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject);wordApp.Visible = false;
//Adds header and footer to each section in the document.
foreach (word.Section section in document.Sections)
{instance fieldEmpty = word.WdFieldType.wdFieldPage;
instance autoText = "AUTOTEXT  \"Page X of Y\" ";
instance preserveFormatting = true;
//Footer.
section.Footers[word.WdHeaderFooterIndex.wdHeaderFooterPrimary].Range.Text = "Internal";
section.Footers[word.WdHeaderFooterIndex.wdHeaderFooterPrimary].Range.ParagraphFormat.Alignment = word.WdParagraphAlignment.wdAlignParagraphLeft;
//Header.       section.
Headers[word.WdHeaderFooterIndex.wdHeaderFooterPrimary].Range.Fields.Add(section.Headers[word.WdHeaderFooterIndex.wdHeaderFooterPrimary].Range,reffieldEmpty, ref autoText, ref preserveFormatting);
section.Headers[word.WdHeaderFooterIndex.wdHeaderFooterPrimary].Range.ParagraphFormat.Alignment = word.WdParagraphAlignment.wdAlignParagraphRight;}
//Saves the document.
document.SaveAs(ref newFilePath, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject);
//Closes the document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word
---------‘Initializes objects.
Dim nullobject As Object = System.Reflection.Missing.Value
Dim filePath As Object = GetPath("original.doc")
Dim newFilePath As Object = GetPath("HeaderFooterOffice.doc")
‘Starts the application.
Dim wordApp As word.Application = New word.Application()
‘Opens the document.
Dim document As word.Document = wordApp.Documents.Open(filePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)wordApp.Visible = False‘Adds header and footer to each section in the document.For Each section As word.Section In document.SectionsDim fieldEmpty As Object = word.WdFieldType.wdFieldPage
‘Footer.    
section.Footers(word.WdHeaderFooterIndex.wdHeaderFooterPrimary).Range.Text = "Internal"            
section.Footers(word.WdHeaderFooterIndex.wdHeaderFooterPrimary).Range.ParagraphFormat.Alignment = word.WdParagraphAlignment.wdAlignParagraphLeft    ‘Header.       section.Headers(word.WdHeaderFooterIndex.wdHeaderFooterPrimary).Range.Fields.Add(section.Headers(word.WdHeaderFooterIndex.wdHeaderFooterPrimary).Range, fieldEmpty, nullobject, nullobject)
section.Headers(word.WdHeaderFooterIndex.wdHeaderFooterPrimary).Range.ParagraphFormat.Alignment = word.WdParagraphAlignment.wdAlignParagraphRightNext‘Saves the document.document.SaveAs(newFilePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)‘Closes the document.doc.Close(nullobject, nullobject, nullobject)
‘Quits the application.
wordApp.Quit()
{% endhighlight   %}
{% endtabs %}


### Using DocIO

You can set the header and footer by using the HeadersFooters property in the Word document section. To access a particular header/footer, you can use the following properties of WHeadersFooters class:

* FirstPageHeader
* FirstPageFooter
* OddHeader
* OddFooter
* EvenHeader
* EvenFooter


{% tabs %}
{% highlight c#  %}
//Opens a Word document.
WordDocument doc = new WordDocument("original.doc");
//Adds header and footer to each section in the document.
foreach (WSection sec in doc.Sections)
{   
  //Header.     WParagraph para = new WParagraph(doc);     
para.AppendField("page", FieldType.FieldPage);   
  para.ParagraphFormat.HorizontalAlignment = HorizontalAlignment.Right;   
  sec.HeadersFooters.Header.Paragraphs.Add(para);   
 //Footer. 
     WParagraph para1 = new WParagraph(doc);     
 para1.AppendText("Internal");   
   para1.ParagraphFormat.HorizontalAlignment = HorizontalAlignment.Left;    
 sec.HeadersFooters.Footer.Paragraphs.Add(para1);}
 //Saves the document.
 doc.Save("HeaderFooterDocIO.doc", FormatType.Doc);
 //Closes the document.
 doc.Close();
{% endhighlight   %}
{% highlight vbnet  %}
‘Opens the Word document.
Dim doc As WordDocument = New WordDocument("original.doc")
‘Adds header and footer to each section in the document.
For Each sec As WSection In doc.Sections     
‘Header.     
Dim para As WParagraph = New WParagraph(doc)  
   para.AppendField("page", FieldType.FieldPage)   
  para.ParagraphFormat.HorizontalAlignment = HorizontalAlignment.Right   
  sec.HeadersFooters.Header.Paragraphs.Add(para)    
 ‘Footer.    
 Dim para1 As WParagraph = New WParagraph(doc)    
 para1.AppendText("Internal")
      para1.ParagraphFormat.HorizontalAlignment = HorizontalAlignment.Left   
   sec.HeadersFooters.Footer.Paragraphs.Add(para1)Next
 ‘Saves the document.
 doc.Save("HeaderFooterDocIO.doc", FormatType.Doc)
 ‘Closes the document.
 doc.Close()
{% endhighlight   %}
{% endtabs %}

N> For more information on inserting Headers and Footers to a Word document using DocIO, you can refer to the online documentation link: <http://docs.syncfusion.com/windowsforms/docio/working-with-sections#working-with-headers-and-footers>



### Character Formatting

Character formatting defines the appearance of the text in a Word document. This section illustrates how to apply character level formatting to the Word document. 

### Using MS Office Interop

Character formatting can be applied to a Word document using Office Automation. You need to set the range of text for formatting. The following code example illustrates how to apply the character formatting to the Word document using the Range properties.

{% tabs %}
{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = System.Reflection.Missing.Value;
instance newFilePath = "CharacterFormattingOffice.doc";
instance falseObj = false;
//Starts the Word application.
word.Application wordApp = new word.Application();
//Creates a new Word document.
wordApp.Documents.Add(ref nullobject, ref nullobject, ref nullobject, refnullobject);
word.Document doc = wordApp.ActiveDocument;
//Defines the range for formatting.
instance start = 0;instance end = 0;
word.Range rng = doc.Range(ref start, ref end);
rng.Text = "New Text";rng.Font.Name = "Arial";
rng.Font.Size = 14;
//Saves the document.
doc.SaveAs(ref newFilePath, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject);
//Closes the document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word-
--------‘Initializes objects.
Dim nullobject As Object = System.Reflection.Missing.Value
Dim newFilePath As Object = "CharacterFormattingOffice.doc"
Dim falseObj As Object = False‘Starts the Word application.
Dim wordApp As word.Application = New word.Application()
‘Creates a new Word document.
wordApp.Documents.Add(nullobject, nullobject, nullobject, nullobject)
Dim doc As word.Document = wordApp.ActiveDocument
‘Defines the range for formatting.
Dim start As Object = 0
Dim endobj As Object = 0
Dim rng As word.Range = doc.Range(start, endobj)
rng.Text = "New Text"rng.Font.Name = "Arial"
rng.Font.Size = 14
‘Saves the document.
doc.SaveAs(newFilePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)‘Closes the document.doc.Close(nullobject, nullobject, nullobject)
‘Quits the application.
wordApp.Quit()
{% endhighlight   %}
{% endtabs %}


### Using DocIO

The following code example illustrates how to apply the character formatting to the Word document using DocIO.

{% tabs %}
{% highlight c#  %}
//Creates a new Word document.
WordDocument doc = new WordDocument();
IWSection section = doc.AddSection();
IWParagraph para = section.AddParagraph();
//Applies formatting.
IWTextRange range = para.AppendText("New Text");
range.CharacterFormat.FontName = "Arial";
range.CharacterFormat.FontSize = 14;
//Saves the document.
doc.Save("CharacterFormattingDocIO.doc", FormatType.Doc);
{% endhighlight   %}
{% highlight vbnet  %}
‘Creates a new Word document.
Dim doc As WordDocument = New WordDocument()
Dim section As IWSection = doc.AddSection()
Dim para As IWParagraph = section.AddParagraph()
‘Applies formatting.
Dim range As IWTextRange = para.AppendText("New Text")
range.CharacterFormat.FontName = "Arial"range.CharacterFormat.FontSize = 14
‘Saves the document.
doc.Save("CharacterFormattingDocIO.doc", FormatType.
{% endhighlight   %}
{% endtabs %}

### Tables

Tables are used to organize information and to display the information in rows and columns. You can also add images or even other tables to the table.

### Using MS Office Interop

The following code example illustrates how to insert a table to a Word document, where the table contains three rows and two columns.

{% tabs %}
{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = System.Reflection.Missing.Value;
instance newFilePath = "TableOffice.doc";
//Starts the Word application.
word.Application wordApp = new word.Application();
//Creates a new document.
wordApp.Documents.Add(ref nullobject, ref nullobject, ref nullobject, refnullobject);
word.Document doc = wordApp.ActiveDocument;
//Inserts table.instance start = 0;
instance end = 0;word.Range tableLocation = doc.Range(ref start, ref end);        
   doc.Tables.Add(tableLocation, 3, 2, ref nullobject, ref nullobject);
//Saves the document.
doc.SaveAs(ref newFilePath, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject);
//Closes the document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word
---------‘Initializes objects.
Dim nullobject As Object = System.Reflection.Missing.Value
Dim newFilePath As Object = "TableOffice.doc"
‘Starts the Word application.
Dim wordApp As word.Application = New word.Application()
‘Creates a new document.
wordApp.Documents.Add(nullobject, nullobject, nullobject, nullobject)
Dim doc As word.Document = wordApp.ActiveDocument
‘Inserts table.
Dim start As Object = 0
Dim endobj As Object = 0
Dim tableLocation As word.Range = doc.Range(start, endobj)doc.Tables.Add(tableLocation, 3, 2, nullobject, nullobject)
‘Saves the document.
doc.SaveAs(newFilePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)
‘Closes the document.
doc.Close(nullobject, nullobject, nullobject)
‘Quits the application.
wordApp.Quit()
{% endhighlight   %}
{% endtabs %}


### Using DocIO

The following code example shows how to insert an empty table to a Word document. The ResetCells() method is used to specify the number of rows and columns in a table.

{% tabs %}
{% highlight c#  %}
//Creates a new Word document.
IWordDocument doc = new WordDocument();
IWSection section = doc.AddSection();
//Adds a table to the document.
IWTable table = section.AddTable();
table.ResetCells(3, 2);
//Saves the document.
doc.Save("TableDocIO.doc");      
{% endhighlight   %}
{% highlight vbnet  %}
‘Creates a new Word document.
Dim doc As IWordDocument = New WordDocument()
Dim section As IWSection = doc.AddSection()
‘Adds a table to the document.
Dim table As IWTable = section.AddTable()
table.ResetCells(3, 2)
‘Saves the document.
doc.Save("TableDocIO.doc")
{% endhighlight   %}
{% endtabs %}

N> For more information on creating tables using DocIO, refer to online documentation link: <http://docs.syncfusion.com/windowsforms/docio/working-with-tables>

Comments

Comments are used to include additional information to a paragraph or text in a Word document. Comments can be added or modified whenever needed and deleted when the comment has served its purpose. Comments are very useful when a document is reviewed. You can insert or delete comments using DocIO and Office Automation.

### Adding Comments Using MS Office Interop

The following code example illustrates how to add comments to a Word document. You need to define the range of text where the comment is to be added.


{% tabs %}
{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = System.Reflection.Missing.Value;
instance newFilePath = "CommentOffice.doc";
//Starts the Word application.
word.Application wordApp = new word.Application();
//Creates a new document.
wordApp.Documents.Add(ref nullobject, ref nullobject, ref nullobject, refnullobject);
word.Document doc = wordApp.ActiveDocument;
//Inserts text to the Word document.
instance start = 0;instance end = 0;
word.Range rng = doc.Range(ref start, ref end);
rng.Text = "New Text";
//Adds comment to the inserted text.
instance text = "Comment goes here";
doc.Comments.Add(rng, ref text);
//Saves the document.
doc.SaveAs(ref newFilePath, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject);
//Closes the document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word
---------‘Initializes objects.
Dim nullobject As Object = System.Reflection.Missing.Value
Dim newFilePath As Object = GetPath("CommentOffice.doc")
‘Starts the Word application.
Dim wordApp As word.Application = New word.Application()
‘Creates a new document.
wordApp.Documents.Add(nullobject, nullobject, nullobject, nullobject)
Dim doc As word.Document = wordApp.ActiveDocument
‘Inserts text to the Word document.
Dim startobj As Object = 0Dim endobj As Object = 0
Dim rng As word.Range = doc.Range(startobj, endobj)
rng.Text = "New Text"
‘Adds comment to the inserted text.
Dim text As Object = "Comment goes here"doc.Comments.Add(rng, text)
‘Saves the document and quits application.
doc.SaveAs(newFilePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)‘Closes the document.doc.Close(nullobject, nullobject, nullobject)
‘Quits the application.
wordApp.Quit()
{% endhighlight   %}
{% endtabs %}


### Adding Comments Using DocIO

You can insert comments to a paragraph or text in a Word document using DocIO. The following code example shows how to insert comments to a Word document.


{% tabs %}
{% highlight c#  %}
//Creates a new Word document.
WordDocument doc = new WordDocument();
IWSection section = doc.AddSection();
//Adds a paragraph to the document.
IWParagraph para = section.AddParagraph();
para.AppendText("New Text");
//Adds comment to the paragraph.
para.AppendComment("Comment goes here");
//Saves the document.
doc.Save("CommentDocIO.doc", FormatType.Doc);
{% endhighlight   %}
{% highlight vbnet  %}
‘Creates a new Word document.
Dim doc As WordDocument = New WordDocument()
Dim section As IWSection = doc.AddSection()
‘Adds a paragraph to the document.
Dim para As IWParagraph = section.AddParagraph()
para.AppendText("New Text")
para.AppendComment("Comment goes here")
‘Saves the document.
doc.Save("CommentDocIO.doc", FormatType.Doc)
{% endhighlight   %}
{% endtabs %}


### Removing Comments Using MS Office Interop

Comments are removed from the Word document after they have served their purpose. The following code example shows how to remove all the comments in a Word document using Office Automation.


{% tabs %}
{% highlight c#  %}
 using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = System.Reflection.Missing.Value;
instance filepath = "Comments.doc";
instance newFilePath = "CommentsRemovedOffice.doc";
//Starts the Word application.
word.Application wordApp = new word.Application(); 
//Opens the Word document.
word.Document document = wordApp.Documents.Open(ref filepath, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject); wordApp.Visible = false;
//Deletes all comments.
document.DeleteAllComments(); 
//Saves the document.
document.SaveAs(ref newFilePath, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject);
 //Closes the document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word
---------‘Initializes objects.
Dim nullobject As Object = System.Reflection.Missing.Value
Dim filepath As Object = "Comments.doc"
Dim newFilePath As Object = "CommentsRemovedOffice.doc"
‘Starts the Word application.
Dim wordApp As word.Application = New word.Application()
‘Opens the Word document.
Dim document As word.Document = wordApp.Documents.Open(filepath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)wordApp.Visible = False
‘Deletes all comments.document.DeleteAllComments()
‘Saves the document.document.SaveAs(newFilePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)
‘Closes the document.
doc.Close(nullobject, nullobject, nullobject)‘Quits the application.wordApp.Quit()
{% endhighlight   %}
{% endtabs %}


### Removing Comments Using DocIO

The CommentsCollection property holds all the comments present in the Word document. The Clear() method can be called to remove all the comments. The following code example illustrates how to remove the comments from a Word document using DocIO.

{% tabs %}
{% highlight c#  %}
//Opens the Word document.
WordDocument doc = new WordDocument("Comments.doc");
//Gets all the comments in the document.
CommentsCollection comments = doc.Comments;
//Removes all the comments from the document.comments.Clear();
//Saves the document.
doc.Save("CommentsRemovedDocIO.doc", FormatType.Doc)
{% endhighlight   %}
{% highlight vbnet  %}
‘Opens the Word document.
Dim doc As WordDocument = New WordDocument("Comments.doc")
‘Gets all the comments in the document.
Dim Comments As CommentsCollection = doc.Comments
‘Removes all the comments from the document.
Comments.Clear()
‘Saves the document.
doc.Save("CommentsRemovedDocIO.doc", FormatType.Doc)
{% endhighlight   %}
{% endtabs %}


N> For more information on working with the comments using DocIO, you can refer to the online documentation link: <http://docs.syncfusion.com/windowsforms/docio/working-with-paragraphs#comments>


### Document Protection

You can protect your Word documents with or without a password, from anyone accidentally or deliberately modifying the Word documents. You can specify the protection type for preserving the Word documents.

### Using MS Office Interop

WdProtectionType property is used to specify the type of protection for the Word document. This property uses the following values:

* wdAllowOnlyComments: Allows only comments to be added to the document.
* wdAllowOnlyFormFields: Allows content to be added to the document through form fields only.
* wdAllowOnlyReading: Allows read-only access to the document.
* wdAllowOnlyRevisions: Allows only revisions to be made to the existing content.
* wdNoProtection: Does not protect  the document.


{% tabs %}
{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = System.Reflection.Missing.Value;
instance filepath = "Document.doc";
instance newFilePath = "FileProtectionOffice.doc";
instance noReset = false;
instance password = System.String.Empty;
instance useIRM = false;
instance enforceStyleLock = false;
//Starts the Word application.
word.Application wordApp = new word.Application();
//Opens the Word document that is to be protected.
word.Document doc = wordApp.Documents.Open(ref filepath, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject);wordApp.Visible = false;
//Sets "Allow only Comments" protection to Word document.
doc.Protect(word.WdProtectionType.wdAllowOnlyComments, ref noReset, refpassword, ref useIRM, ref enforceStyleLock);
//Saves the document.
doc.SaveAs(ref newFilePath, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject);//Closes the document.document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quits the application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
 Imports word = Microsoft.Office.Interop.Word
----------------‘Initializes objects.
Dim nullobject As Object = System.Reflection.Missing.Value
Dim filepath As Object = "Document.doc"
Dim newFilePath As Object = "FileProtectionOffice.doc"
Dim noReset As Object = False
Dim password As Object = System.String.Empty
Dim useIRM As Object = FalseDim enforceStyleLock As Object = False‘Starts the Word application.
Dim wordApp As word.Application = New word.Application()
‘Opens the Word document that is to be protected.
Dim doc As word.Document = wordApp.Documents.Open(filepath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)wordApp.Visible = False
‘Sets "Allow only Comments" protection to the Word document.
doc.Protect(word.WdProtectionType.wdAllowOnlyComments, noReset, password, useIRM, enforceStyleLock)
‘Saves the document.
doc.SaveAs(newFilePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)‘Closes the document.doc.Close(nullobject, nullobject, nullobject)
‘Quits the application.wordApp.Quit()
{% endhighlight   %}
{% endtabs %}


### Using DocIO

DocIO uses ProtectionType property to specify the protection type of the Word document. This property uses the following values:

* AllowOnlyComments: Allows only comments to be added to the document.
* AllowOnlyFormFields: Allows content to be added to the document through form fields only.
* AllowOnlyRevisions: Allows only revisions to be made to the existing content.
* AllowOnlyReading: All kinds of editing are restricted here and it makes the Word document as read-only document.
* NoProtection: Does not protect the document.


{% tabs %}
{% highlight c#  %}
//Opens the Word document.
WordDocument doc = new WordDocument("Document.doc");
//Sets "Allow only Comments" protection to Word document.
doc.ProtectionType = ProtectionType.AllowOnlyComments;
//Saves the document.
doc.Save("FileProtectionDocIO.doc");
{% endhighlight   %}
{% highlight vbnet  %}
‘Opens the Word document.
Dim doc As WordDocument = New WordDocument("Document.doc")
‘Sets "Allow only Comments" protection to Word document.
Doc.ProtectionType = ProtectionType.AllowOnlyComments;
‘Saves the document.
doc.Save("FileProtectionDocIO.doc")
{% endhighlight   %}
{% endtabs %}


Refer to the online documentation link for more details about ways to protect the Word documents using DocIO.<http://docs.syncfusion.com/windowsforms/docio/migration-from-microsoft-office-automation-to-essential-docio#document-protection>


### Table of Contents

Table of contents can be generated by applying the heading styles to text in a Word document. To create the table of contents in Microsoft Word, click Table of Contents from the Table of Contents group on the References tab. 

### Using MS Office Interop

The following code example shows how to insert and update table of contents in a Word document.


{% tabs %}
{% highlight c#  %}
using word = Microsoft.Office.Interop.Word;
---------//Initializes objects.
instance nullobject = System.Reflection.Missing.Value;
instance filepath = "TOCDocument.doc";
instance newFilePath = "TOCUpdatedOffice.doc";
instance trueobj = true;    
 //Starts the Word application.
word.Application wordApp = new word.Application();
//Opens the Word document.
word.Document document = wordApp.Documents.Open(ref filepath, ref nullobject,ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject);wordApp.Visible = false;
//Defines the range for TOC in the document.
instance tocstart = 0;instance tocend = 0;
word.Range rngToc = document.Range(ref tocstart, ref tocend);
//Adds TOC.
word.TableOfContents toc = document.TablesOfContents.Add(rngToc, ref trueobj,ref nullobject, ref nullobject, ref nullobject, ref nullobject, ref trueobj,ref trueobj, ref trueobj, ref trueobj, ref trueobj, ref trueobj);
//Updates TOC
.toc.Update();
//Saves the document.
document.SaveAs(ref newFilePath, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject, ref nullobject, ref nullobject, refnullobject, ref nullobject, ref nullobject);
//Closes the document.
document.Close(ref nullobject, ref nullobject, ref nullobject);
//Quit the application.
wordApp.Quit(ref nullobject, ref nullobject, ref nullobject);
{% endhighlight   %}
{% highlight vbnet  %}
Imports word = Microsoft.Office.Interop.Word
----------------‘Initializes objects.
Dim nullobject As Object = System.Reflection.Missing.Value
Dim filepath As Object = "TOCDocument.doc"
Dim newFilePath As Object = "TOCUpdatedOffice.doc"
Dim trueobj As Object = True‘Starts the application.
Dim wordApp As word.Application = New word.Application()
‘Opens the document.
Dim document As word.Document = wordApp.Documents.Open(filepath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)wordApp.Visible = False‘Defines the range for TOC in the document.Dim tocstart As Object = 0
Dim tocend As Object = 0
Dim rngToc As word.Range = document.Range(tocstart, tocend)
‘Adds TOC.
Dim TOC As word.TableOfContents = document.TablesOfContents.Add(rngToc, trueobj, nullobject, nullobject, nullobject, nullobject, trueobj, trueobj, trueobj, trueobj, trueobj, trueobj)‘Updates TOC.TOC.Update()
‘Saves the document.
document.SaveAs(newFilePath, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject, nullobject)
‘Closes the document.
doc.Close(nullobject, nullobject, nullobject)
‘Quits the application.
wordApp.Quit()
{% endhighlight   %}
{% endtabs %}


### Using DocIO

The following code example illustrates how to insert and update the table of contents in a Word document using DocIO.


{% tabs %}
{% highlight c#  %}
//Opens the Word document.
WordDocument doc = new WordDocument("TOCDocument.doc", FormatType.Doc);
IWSection sec = doc.Sections[0];
//Appends TOC to the first paragraph of the document.
WParagraph para = new WParagraph(doc);
TableOfContent toc = para.AppendTOC(1, 3);
sec.Paragraphs.Insert(0, para);
//Updates table of contents.
doc.UpdateTableOfContents();
//Saves the document.
doc.Save("TOCUpdatedDocIO.doc", FormatType.Doc);
{% endhighlight   %}
{% highlight vbnet  %}
‘Opens the Word document.
Dim doc As WordDocument = New WordDocument("TOCDocument.doc", FormatType.Doc)
Dim sec As IWSection = doc.Sections(0)
‘Appends TOC to the first paragraph of the document.
Dim para As WParagraph = New WParagraph(doc)
Dim TOC As TableOfContent = para.AppendTOC(1, 3)
sec.Paragraphs.Insert(0, para)
‘Updates table of contents.
doc.UpdateTableOfContents()
‘Saves the document.
doc.Save("TOCUpdatedDocIO.doc", FormatType.Doc)
{% endhighlight   %}
{% endtabs %}


Refer to the online documentation link for more information about adding the table of contents to the Word document using DocIO: <http://docs.syncfusion.com/windowsforms/docio/migration-from-microsoft-office-automation-to-essential-docio#table-of-contents>







