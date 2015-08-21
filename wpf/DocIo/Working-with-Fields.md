---
layout: post
title: Working-with-Fields
description: working with fields
platform: wpf
control: DocIO
documentation: ug
---

# Working with Fields

Fields are special elements of a Word document. To insert a field, click Insert menu, and then click Field option in Microsoft Word.



![](Working-with-Fields_images/Working-with-Fields_img1.png)



Fields are widely used for Mail Merge. In a Word document, almost every field consists of the field start, marker text that specifies the type of the field. Fields are preserved with field separator marker, field value, and field end marker.

WField class represents a field in a Word document. There are many types of fields.



![](Working-with-Fields_images/Working-with-Fields_img2.png)



Gets or specifies the type of a field by using the FieldType property. WField class also has the TextFormat property that specifies the text format for the field. There are four different types of text formats for fields.

* None: No text formatting.
* Uppercase: Uppercase text formatting.
* Lowercase: Lowercase text formatting.
* FirstCapital: First capital text formatting.
* Titlecase: Title case text formatting.

## Adding a Field to a Paragraph

You can use the AppendField method of the WParagraph class to add new fields to a paragraph. When you add field to a paragraph, all the field markers are automatically added to the paragraph. 

There are special fields like Form Field, Merge Field, Embed Field, and Seq Field. For details, refer to the WFormField, WMergeField, WEmbedField, and WSeqField documentation.

Class Hierarchy

WTextRange

|

WField

Public Constructors

_Public Constructors_

<table>
<tr>
<th>
Constructor Name</th><th>
Description</th></tr>
<tr>
<td>
WField.WField (IWordDocument)</td><td>
Initializes a new instance of the WField class. </td></tr>
</table>
Public Properties

_Public Properties_

<table>
<tr>
<th>
Property Name</th><th>
Description</th></tr>
<tr>
<td>
EntityType</td><td>
Gets the type of the entity.  </td></tr>
<tr>
<td>
FieldPattern</td><td>
Gets or sets the field pattern information.  </td></tr>
<tr>
<td>
FieldType</td><td>
Gets or sets the field type information</td></tr>
<tr>
<td>
FieldValue</td><td>
Gets the field value.  </td></tr>
<tr>
<td>
TextFormat</td><td>
Gets or sets the regular text format information.  </td></tr>
</table>


{% highlight c# %}
IWSection section = doc.AddSection();IWParagraph paragraph = section.AddParagraph();paragraph.AppendText("Testing writing Merge Fields into Header");section.PageSetup.DifferentFirstPage = true;section.PageSetup.DifferentOddAndEvenPages = true;paragraph = new WParagraph(doc);paragraph.AppendText("[ FIRST PAGE Header ]");section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph);paragraph = new WParagraph(doc);//Appends field.paragraph.AppendField("Field's Name", FieldType.FieldMergeField);section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph);paragraph = new WParagraph(doc);paragraph.AppendText("[ FIRST PAGE Footer ]\r");section.HeadersFooters.FirstPageFooter.Paragraphs.Add(paragraph);
{% endhighlight  %}
{% highlight c# %}
Dim section As IWSection = doc.AddSection()Dim paragraph As IWParagraph = section.AddParagraph()paragraph.AppendText("Testing writing Merge Fields into Header")section.PageSetup.DifferentFirstPage = Truesection.PageSetup.DifferentOddAndEvenPages = Trueparagraph = New WParagraph(doc)paragraph.AppendText("[ FIRST PAGE Header ]")section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph)paragraph = New WParagraph(doc)'Appends field.paragraph.AppendField("Field's Name", FieldType.FieldMergeField)section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph)paragraph = New WParagraph(doc)paragraph.AppendText("[ FIRST PAGE Footer ]" and Constants.VB.NETCr)section.HeadersFooters.FirstPageFooter.Paragraphs.Add(paragraph)
{% endhighlight  %}

## Merge Field

WMergeField class represents a merge field in a Word document. To add a merge field in Microsoft Word, click the Insert menu, click Field, and then click MergeField. Merge field is suitable for mail merge because it is easy to set the user's data inside it. You can use the following properties to peform mail merge:

* FieldName: Specifies the name of the field.
* TextBefore andTextAfter: Specifies text that is displayed before and after the merge field.
* NumberFormat andDateFormat: Specifies number and date format respectively.

NumberFormat and DateFormat properties do not have an equivalent in Word MergeField.

Class Hierarchy

WTextRange

|

       WField

    	    |    

WMergeField

Public Constructors

_Public Constructors_

<table>
<tr>
<th>
Constructor Name</th><th>
Description</th></tr>
<tr>
<td>
WMergeField.WMergeField (IWordDocument)</td><td>
Initializes a new instance of the WMergeField class. </td></tr>
</table>


Public Properties

_Public Properties_

<table>
<tr>
<th>
Property Name</th><th>
Description</th></tr>
<tr>
<td>
DateFormat</td><td>
Gets the date format.  </td></tr>
<tr>
<td>
EntityType</td><td>
Gets the type of the entity.  </td></tr>
<tr>
<td>
FieldName</td><td>
Gets or sets the field name.</td></tr>
<tr>
<td>
NumberFormat</td><td>
Gets the number format.  </td></tr>
<tr>
<td>
Prefix</td><td>
Gets the prefix of merge field.</td></tr>
<tr>
<td>
TextAfter</td><td>
Gets or sets the text after merge field.  </td></tr>
<tr>
<td>
TextBefore</td><td>
Gets or sets the text before merge field.  </td></tr>
</table>
The following code example illustrates how to add a merge field to the header and footer of a document.



{% highlight c# %}
IWSection section = doc.AddSection();IWParagraph paragraph = section.AddParagraph();paragraph.AppendText("Testing writing Merge Fields into Header");section.PageSetup.DifferentFirstPage = true;section.PageSetup.DifferentOddAndEvenPages = true;paragraph = new WParagraph(doc);paragraph.AppendText("[ FIRST PAGE Header ]");section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph);paragraph = new WParagraph(doc);paragraph.AppendField("Field's Name", FieldType.FieldMergeField);section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph);paragraph = new WParagraph(doc);paragraph.AppendText("[ FIRST PAGE Footer ]\r");section.HeadersFooters.FirstPageFooter.Paragraphs.Add(paragraph);
{% endhighlight  %}
{% highlight vbnet  %}
Dim section As IWSection = doc.AddSection()Dim paragraph As IWParagraph = section.AddParagraph()paragraph.AppendText("Testing writing Merge Fields into Header")section.PageSetup.DifferentFirstPage = Truesection.PageSetup.DifferentOddAndEvenPages = Trueparagraph = New WParagraph(doc)paragraph.AppendText("[ FIRST PAGE Header ]")section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph)paragraph = New WParagraph(doc)paragraph.AppendField("Field's Name", FieldType.FieldMergeField)section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph)paragraph = New WParagraph(doc)paragraph.AppendText("[ FIRST PAGE Footer ]" and Constants.VB.NETCr)section.HeadersFooters.FirstPageFooter.Paragraphs.Add(paragraph)
{% endhighlight  %}

## Embed Field

WEmbedField class represents an embed field type in a Word document. Word does not allow to create an embed field type manually (by using Microsoft Word interface). This field is used when the document has embedded objects. This field usually points to the container in the document that encloses the embedded instance.

> Note: Modification of WEmbedField properties can cause document corruption or incorrect document preservation. DocIO preserves only fields of this type.

Class Hierarchy

WTextRange

|

WField

|

    		 WEmbedField

Public Properties

_Public Properties_

<table>
<tr>
<th>
Property Name</th><th>
Description</th></tr>
<tr>
<td>
EntityType</td><td>
Gets the type of the entity.  </td></tr>
</table>

## Seq Field

WSeqField class represents a sequence field type in the Word document. To add a sequence field in Microsoft Word, click the Insert menu, Field, and then Seq.

You can use the NumberFormat property to set the numbering format for the fields and the CaptionName property to set the name of the caption.

Public Constructors

_Table80: Public Constructors_

<table>
<tr>
<th>
Constructor Name</th><th>
Description</th></tr>
<tr>
<td>
WSeqField.WSeqField (IWordDocument)</td><td>
Initializes a new instance of the WSeqField class.</td></tr>
</table>
Public Properties

_Table81: Public Properties_

<table>
<tr>
<th>
Property Name</th><th>
Description</th></tr>
<tr>
<td>
CaptionName</td><td>
Gets or sets the caption name.  </td></tr>
<tr>
<td>
EntityType</td><td>
Gets the type of the entity.  </td></tr>
<tr>
<td>
FormattingString</td><td>
Gets the formatting string.  </td></tr>
<tr>
<td>
NumberFormat</td><td>
Gets or sets the type of caption numbering. It includes the following options.* Number* Roman* Alphabetic</td></tr>
</table>



{% highlight c# %}
WSeqField field = ( WSeqField )paragraph.AppendField("Sequence Field", FieldType.FieldSequence );field.CaptionName = "SequenceField";field.NumberFormat = CaptionNumberingFormat.Alphabetic;</td></tr>
{% endhighlight  %}
{% highlight vbnet %}
Dim field As WSeqField = CType(paragraph.AppendField("Sequence Field", FieldType.FieldSequence), WSeqField)field.CaptionName = "SequenceField"field.NumberFormat = CaptionNumberingFormat.Alphabetic</td></tr>
{% endhighlight  %}

## Document Variable

A Document Variable is stored as part of a document or template. Document variables store information about the document. These are useful for document automation because they allow the programmer to store information for future use. For example, some firms use document variables to store Client and Author information, for use in the footer or field code purposes.

Essential DocIO provides support to work with these document variables. You can get or set the variables by using the variable name or index.

* Document variables are accessible through the IDocument.Variables property. 
* Variables are added to the document by using the IDocument.Variables.Add(string variableName, string variableValue) method.
* Variables are removed from the document by using the IDocument.Variables.Remove(string variableName) method.

You can refer these fields in other parts of the document easily. For example, you can use the IWParagraph.AppendField(string fieldName, FieldType type) method, where the 1st argument is the name of the document field and the 2nd argument is FiledType.FieldDocVariable.



![](Working-with-Fields_images/Working-with-Fields_img3.png)





{% highlight c# %}
WordDocument doc = new WordDocument();doc.Open("Sample.doc");DocVariables v = document1.Variables;//Adds a variable.v.Add("var1", "Author Name");//Adds or modifies variables.v["var2"] = "change name";Console.WriteLine("Number of Variables:" + document1.Variables.Count.ToString());Console.WriteLine("Variable Name:" + document1.Variables.GetNameByIndex(0));Console.WriteLine("Varaible Value:" + document1.Variables.GetValueByIndex(0));doc.Save("SampleModified.doc");
{% endhighlight  %}
{% highlight vbnet %}
Dim doc As WordDocument = New WordDocument()doc.Open("Sample.doc")Dim v As DocVariables = document1.Variables'Adds a variable.v.Add("var1", "Author Name")'Add or modifies variables.v("var2") = "change name"Console.WriteLine("Number of Variables:" + document1.Variables.Count.ToString())Console.WriteLine("Variable Name:" + document1.Variables.GetNameByIndex(0))Console.WriteLine("Varaible Value:" + document1.Variables.GetValueByIndex(0))doc.Save("SampleModified.doc")
{% endhighlight  %}

## Updating Fields

Field in a Word document is a placeholder of data that changes on field update. A field contains a field code, field separator, field result, and field end. The field code includes information on how to calculate and update the field result. The field result specifies the resultant value of the field. Field updating engine calculates the resultant value based on the field code information and updates the field result with the new value. The supported fields are as follows:

* = (formula field)
* DATE
* TIME
* DOCVARIABLE 
* DOCPROPERTY
* COMPARE
* IF
* NEXTIF
* MERGEREC
* MERGESEQ
* SECTION
* Cross-Reference

= (formula field)

This field is an expression that contains any combination of numbers, bookmarks that refer to numbers, fields resulting in numbers, and the available operators and methods. The expression can refer to values in a table and values returned by methods.

DATE and TIME

This field displays the current date-time, in the format specified by date-time picture switch.

Syntax

{ DATE [\@ "Date-Time Picture"] }

{ TIME [\@ "Date-Time Picture"] }

DOCVARIABLE 

This field displays the value of the specified document variable.

Syntax

{DOCVARIABLE "Name”}

DOCPROPERTY

This field displays the value of the specified document property.

Syntax

{DOCPROPERTY "Name”}

COMPARE

This field compares two expressions and displays the result as "1" when the result of comparison is true_,_ or "0" (zero) when the comparison is false.

Syntax

{COMPARE Expression1 Operator Expression2} 

IF

This field compares two expressions and displays the true text when the result of comparison is true, or displays the false text when the result of comparison is false.

Syntax

{IF Expression1 Operator Expression2 TrueText FalseText}

NEXTIF

This field compares two expressions. When the comparison result is true, the next data record is merged into the current merge document. When the comparison result is false, the next data record is merged into a new merge document.

Syntax

{NEXTIF Expression1 Operator Expression2}

MERGESEQ

This field numbers all the merged records of a mail merge. The number may be different from the value that is inserted by the MERGEREC field.

Syntax 

{MERGESEQ}

MERGEREC

This field displays the ordinal position of the current data record in a merged document. The number reflects any sorting or filtering that you applied to the data source before the merge. 

Syntax 

{MERGEREC}

SECTION

This field displays the number of the current section. 

Syntax 

{SECTION}

Cross-Reference

Insert the reference to the Bookmark.

Syntax 

REF BookmarkName [Switches]



> Note: Page number and Paragraph number options are not supported in Silverlight, WinRT and Windows Phone applications while updating Cross reference field.

### Known Limitations

The following are the known limitations:

* Currently shapes, drawing canvas, and table auto resizing are not supported in Word to PDF lay outing as they may lead to update the incorrect page number.

The following code example illustrates how to update the fields present in a document.



{% highlight c# %}



//Opens a Word document.

WordDocument document = new WordDocument("Input.doc");

//Updates the fields present in a document.

document.UpdateDocumentFields();

//Saves a document.

document.Save("Sample.doc", FormatType.Doc);


{% endhighlight  %}
{% highlight vbnet %}






'Opens a Word document.

Dim document As WordDocument = New WordDocument("Input.doc")

'Updates the fields present in a document.

document.UpdateDocumentFields()

'Saves a document.

document.Save("Sample.doc", FormatType.Doc)
{% endhighlight  %}

## Cross Reference

A Cross-Reference is a pointer or link to an item that is in another location in a document. You can create Cross-References to bookmarks in Word documents using Essential DocIO. When you add the Cross- Reference, you can specify the reference with/without hyperlink. While updating the Bookmark, Cross-Reference to the document, the specified bookmark should be preserved in that document or else it preserves field value as Error! Reference source not found.



To add a Cross-Reference field in Microsoft Word, click the Insert menu and then click Cross-reference. Cross-reference is suitable to create reference to the contents in the document and it is easy to set using the bookmarks in the document.



![](Working-with-Fields_images/Working-with-Fields_img4.png)



You can use the following reference options to insert bookmark cross-reference field:

* ContentText – Inserts the Reference field with field value as Bookmark Text i.e. the text between the bookmark start and end. When the Cross Reference is inserted within the Bookmark Start and End Error! Not a valid bookmark self-reference exception is thrown.
* AboveBelow – Inserts the Reference field with the field value as Above, when the bookmark is below the current context, and Below, when the bookmark is above the current context.
* PageNumber – Inserts the Page Reference field with page number of the specified Bookmark as field value. 
* NumberRelativeContext – Inserts the Reference field with the paragraph number with as much of its relative position in the outline numbered list as necessary to identify the specified Bookmark as field value. 
* NumberNoContext - Inserts the Reference field with the paragraph number without its relative position of the specified Bookmark as field value.
* NumberFullContext - Inserts the Reference field with the field value as complete paragraph number of the specified Bookmark as field value. 

The following code example illustrates how to append cross reference in the document.



{% highlight c# %}
//Creates a new Word document instanceWordDocument doc = new WordDocument();//Add a new Section in the Word documentIWSection section = doc.AddSection();//Add new Paragraph in the Word documentIWParagraph paragraph = section.AddParagraph();//Add Text, Bookmark Start and End in the Paragraphparagraph.AppendText("Bookmark starts here ");paragraph.AppendBookmarkStart("Test");paragraph.AppendText("Bookmark Text");paragraph.AppendBookmarkEnd("Test");paragraph.AppendText("Bookmark ends here ");section.AddParagraph();paragraph = section.AddParagraph()as WParagraph;;//Get the collections of Bookmark starts in the word documentList<Entity> items = doc.GetCrossReferenceItems(ReferenceType.Bookmark);paragraph.AppendText("Bookmark Cross Reference starts here ");//Append The Cross Reference for Bookmark “Test” with ContentText as ReferenceKindparagraph.AppendCrossReference(ReferenceType.Bookmark, ReferenceKind.ContentText, items[0], true, false, false, string.Empty);//Update Document Fieldsdoc.UpdateDocumentFields();//Saves a documentdoc.Save("BookmarkCrossReference.docx");
{% endhighlight  %}
{% highlight vbnet  %}
'Creates a new Word document instanceDim doc As New WordDocument()' Add a new Section in the Word documentDim section As IWSection = doc.AddSection()' Add new Paragraph in the Word documentDim paragraph As IWParagraph = section.AddParagraph()'Add Text, Bookmark Start and End in the Paragraphparagraph.AppendText("Bookmark starts here ");paragraph.AppendBookmarkStart("Test");paragraph.AppendText("Bookmark Text");paragraph.AppendBookmarkEnd("Test");paragraph.AppendText("Bookmark ends here ");section.AddParagraph();paragraph = section.AddParagraph()as WParagraph;;'Get the collections of Bookmark starts in the word documentDim items As List<Entity> = document.GetCrossReferenceItems(ReferenceType.Bookmark);paragraph.AppendText("Bookmark Cross Reference starts here ");'Append The Cross Reference for Bookmark “Test” with ContentText as ReferenceKindparagraph.AppendCrossReference(ReferenceType.Bookmark, ReferenceKind.ContentText, items[0], true, false, false, string.Empty);'Update Document Fieldsdoc.UpdateDocumentFields();'Saves a documentdoc.Save("BookmarkCrossReference.docx");
{% endhighlight  %}


