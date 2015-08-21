---
layout: post
title: Find-and-Replace
description: find and replace
platform: wpf
control: DocIO
documentation: ug
---

# Find and Replace

This feature helps find particular content in a document and replace it with some other content. It is one of the most remarkable features available in Essential DocIO, which lets you to find a string, document element, or bookmarks available in a Word document, and replace the selected element with another document element. To use this functionality effectively, you need to understand the following concepts:

This section elaborates the possible ways to perform the find and replacement operation effectively and describes the APIs involved in this technique.

* TextSelction
* TextBodySelection
* TextBodyPart
* Find
* Replace

## TextSelection


This represents selected text in a Word document. It is equivalent to selecting a word or group of words by using mouse in Microsoft Word. However, the following are limitations in using the TextSelection class:

* Text selection must be continuous (must not be split).
* Selected text should remain within a single paragraph, and will be ignored if it extends to more than one paragraph.

TextSelection class internally uses the Find and FindAll methods to select text. Please refer to the Find section topic to get more information about Find and FIndAll methods.

Public Constructors

_Public Constructor_

<table>
<tr>
<th>
Constructor Name</th><th>
Description</th></tr>
<tr>
<td>
TextSelection.TextSelection(paragraph, startCharPos, endCharPos)</td><td>
Initializes a new instance of the TextSelection class.</td></tr>
</table>

## Parameter Description

* paragraph: Specifies the paragraph that contains text to be selected.
* startCharPos: Specifies the starting position of text selection in a paragraph.
* endCharPos: Specifies the ending position of text selection in a paragraph.

The following code example illustrates how to instantiate a TextSelection class.



{% highlight  c# %}



TextSelection selection = new TextSelection(paragraph, 0, 10);

{% endhighlight   %}
{% highlight  vbnet %}



Dim selection As New TextSelection(paragraph, 0, 10)
{% endhighlight  %}

Public Properties

_Public Properties_

<table>
<tr>
<th>
Property Name</th><th>
Description</th></tr>
<tr>
<td>
Count</td><td>
Gets the count of the text chunks.</td></tr>
<tr>
<td>
SelectedText</td><td>
Gets the selected text.  </td></tr>
</table>
Public Methods

_Public Methods_

<table>
<tr>
<th>
Method Name</th><th>
Description</th></tr>
<tr>
<td>
GetAsOneRange</td><td>
Gets the text ranges in the selected text and combines them to a single text range.</td></tr>
<tr>
<td>
GetEnumerator</td><td>
Gets an enumerator that iterates through a collection.</td></tr>
<tr>
<td>
GetRanges</td><td>
Gets all the text ranges in the selected text and returns them as an array.</td></tr>
<tr>
<td>
this[int]</td><td>
Gets the System.String at the specified index.  </td></tr>
</table>


> Note: TextSelection and GetAsOneRange should not be used for text replacement.

The following code example illustrates how to use the TextSelection class with the Find Method. Refer to the Find section to know more about Find method.



{% highlight  c# %}

TextSelection rangesHolder1 = document.Find( "The PlaceHolder1", false, false );

{% endhighlight   %}
{% highlight  vbnet %}



Dim rangesHolder1 As TextSelection = document.Find("The PlaceHolder1", False, False)
{% endhighlight  %}

## TextBodyPart

TextBodyPart class contains the collection of body items (it means that TextBodyPart can contain paragraphs, tables, and even sections). These text body parts are the members used to construct a word document. TextBodyPart is usually used with the Bookmark Navigator.

> Note: TextBodyPart contains the copy of objects from the documents (paragraphs, tables, sections, and so on). So, if you modify the content of the TextBodyPart, it will not affect the objects inside the document.



Public Constructors

_Public Constructors_

<table>
<tr>
<th>
Constructors </th><th>
Description</th></tr>
<tr>
<td>
TextBodyPart.TextBodyPart ()</td><td>
Initializes a new instance of the TextBodyPart class.</td></tr>
<tr>
<td>
TextBodyPart.TextBodyPart (TextBodySelection)</td><td>
Initializes a new instance of the TextBodyPart class with respect to TextBodySelection class. Refer to the section TextBodySelection to know more about this.</td></tr>
<tr>
<td>
TextBodyPart.TextBodyPart (TextSelection)</td><td>
Initializes a new instance of the TextBodyPart class with respect to TextSelection class. Refer to the section TextSelection to know about this.</td></tr>
<tr>
<td>
TextBodyPart.TextBodyPart (WordDocument)</td><td>
Initializes a new instance of the TextBodyPart class with respect to WordDocument class. Refer to the section WordDocument to know more about this.</td></tr>
</table>

Public Properties

_Public Properties_

<table>
<tr>
<th>
Property </th><th>
Description</th></tr>
<tr>
<td>
BodyItems</td><td>
Gets the body items.  </td></tr>
</table>


Public Methods

_Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
Clear</td><td>
Clears the specified instance. </td></tr>
<tr>
<td>
Copy</td><td>
Copies the specified item.</td></tr>
<tr>
<td>
PasteAfter</td><td>
Pastes ParagraphItem or TextBodyItem after the specified item.</td></tr>
<tr>
<td>
PasteAt</td><td>
Pastes ITextBody at the specified position.</td></tr>
<tr>
<td>
PasteAtEnd</td><td>
Pastes ITextBody at the end of the textbody.  </td></tr>
<tr>
<td>
Close</td><td>
Closes the TextBodyPart instance.</td></tr>
</table>


The following code example illustrates how to use the TextBodyPart class with the BookmarksNavigator.


{% highlight  c# %}

WordDocument doc = new WordDocument( "sample.doc" );

BookmarksNavigator bn = new BookmarksNavigator(doc);

bn.MoveToBookmark("bookmark1");

TextBodyPart bodyPart = bn.GetBookmarkContent();

{% endhighlight   %}


{% highlight  vbnet %}
Dim doc As WordDocument = New WordDocument("sample.doc")

Dim bn As BookmarksNavigator = New BookmarksNavigator(doc)

bn.MoveToBookmark("bookmark1")

Dim bodyPart As TextBodyPart = bn.GetBookmarkContent()
{% endhighlight   %}

## TextBodySelection

This class lets you select text body items from the TextBodyPart class. TextBodyPart contains text body items, which you can select through the TextBodySelection class based on your requirement.

For example, you have the following Contents:

Text-NEED TO COPY

<table>
<tr>
<td>
</td><td>
</td></tr>
<tr>
<td>
</td><td>
</td></tr>
</table>

### Another text-THIS TEXT 

Now, you may want to copy the text "NEED TO COPY", Table and "THIS TEXT" and paste in another location.

The following tree structure denotes the DocIO representation of the above content at its instance model level.

 TextBody

1. [0]Paragraph
* [0]TextRange – "Text"
* [1]TextRange – "NEED TO"
* [2]TextRange – "COPY"
2. •[1]Table
3. •[2]Paragraph
* [0]TextRange – "THIS"
* [1]TextRange – "TEXT"
* [2]TextRange – "Other Text"



The following code example shows how to select particular items from the above tree structure.



{% highlight  c# %}

TextBodySelection bodySelection = new TextBodySelection( body, 0, 2, 1, 1 );

{% endhighlight   %}
{% highlight  vbnet %}



Dim bodySelection As New TextBodySelection(body, 0, 2, 1, 1)

{% endhighlight   %}

### Parameter Description

* body: Denotes the text body.
* 0: Denotes the paragraph starting index.
* 2: Denotes the paragraph ending index.
* 1: Denotes the paragraph item starting index in first paragraph.
* 1: Denotes the paragraph item ending index in last paragraph.

Public Constructors

_Public Constructors_

<table>
<tr>
<th>
Constructors </th><th>
Description</th></tr>
<tr>
<td>
TextBodySelection.TextBodySelection (ITextBody, int, int, int, int)</td><td>
Initializes a new instance of the TextBodySelection class with the textbody, start paragraph index, end paragraph index, start paragraph item index, and end paragraph item index.</td></tr>
<tr>
<td>
TextBodySelection.TextBodySelection (ParagraphItem, ParagraphItem)</td><td>
Initializes a new instance of the TextBodySelection class with start paragraph item and end paragraph item.</td></tr>
</table>


Public Properties

_Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
ItemEndIndex</td><td>
Gets or sets the end index of the text body item.  </td></tr>
<tr>
<td>
ItemStartIndex</td><td>
Gets or sets the start index of the text body item.  </td></tr>
<tr>
<td>
ParagraphItemEndIndex</td><td>
Gets or sets the end index of the paragraph item.  </td></tr>
<tr>
<td>
ParagraphItemStartIndex</td><td>
Gets or sets the start index of the paragraph item.  </td></tr>
<tr>
<td>
TextBody</td><td>
Gets the text body.  </td></tr>
</table>


You can utilize the Copy and Paste methods of TextBodyPart of the TextBodySelection to copy and paste the text and body elements at any position in a document. The following code example illustrates this.




{% highlight  c# %}


//Creates TextBodySelection and selects the items of interest.

TextBodySelection textSel = new TextBodySelection(sec.Body, 0, lastItemIndex, 0, lastPItemIndex);



//Creates TextBodyPart and copies the selected items.

TextBodyPart replacePart = new TextBodyPart(doc);

replacePart.Copy(textSel);



//Pastes the copied content at the end of the text body.

replacePart.PasteAt(txtbdy,itemIndex);


{% endhighlight   %}
{% highlight  vbnet %}




'Creates TextBodySelection and selects the items of interest.

Dim textSel As TextBodySelection = New TextBodySelection(sec.Body, 0, lastItemIndex, 0, lastPItemIndex)



'Creates TextBodyPart and copies the selected items.

Dim replacePart As TextBodyPart = New TextBodyPart(doc)

replacePart.Copy(textSel)



'Pastes the copied text at the end of the text body.

replacePart.PasteAt(txtbdy, itemIndex)
{% endhighlight   %}

## Find

Find option is a common feature in most applications. Essential DocIO provides this feature to find a particular item in a Word document and manipulate operations based on that. The following are the various types of Find options available in Essential DocIO:

* Find
* FindAll
* FindNext
* ResetFindNext
* FindSingleLine
* FindNextSingleLine

### Find and FindAll Methods

Find method is used to find an entry with a specified text of regular expression in the Word document and it has two overloads:

* document.Find(RegularExpression.Regex pattern): Finds text based on the given regex pattern.
* document.Find(string givenString, bool wholeWord, bool caseSensitive): Finds given string that matches the case and whole word. Please refer to the following parameters description.

### Parameter Description

* givenString: Text to find.
* caseSensitive: If this option is set to _true_, only strings that match the case of the whole word will be returned.
* wholeWord: If this option is set to _true_, only strings that match the whole word will be returned. The case of the words will not be matched.



{% highlight  c# %}

TextSelection rangesHolder1 = document.Find( "The PlaceHolder1", false, false );
{% endhighlight   %}
{% highlight  vbnet %}




Dim rangesHolder1 As TextSelection = document.Find("The PlaceHolder1", False, False)
{% endhighlight   %}


FindAll method also finds the given string in a Word document, but the difference is that it returns all possible occurrences of the given string:

* document.FindAll(RegularExpression.Regex pattern): Finds text based on the given regex pattern and returns all possible matches.
* document.FindAll(string givenString, bool wholeWord, bool caseSensitive): Finds strings that match the case and whole word  and returns all possible matches.




{% highlight  c# %}
TextSelection[] rangesHolder1 = document.FindAll( "The PlaceHolder1", false, false );
{% endhighlight   %}
{% highlight  vbnet %}




Dim rangesHolder1 As TextSelection() = document.Find("The PlaceHolder1", False, False)
{% endhighlight   %}


### FindNext Method

You can find a particular string from a paragraph region or table by using the FindNext method. It has two overloads.

* document.FindNext(TextBodyItem startBodyItem, RegularExpression.Regex pattern): Finds the next entry based on the given regex pattern from the start text body item.
* Document.FindNext(TextBodyItem startBodyItem, string givenString, bool caseSensitive, bool wholeWord): Finds the next occurrence of the given string that matches the case and whole word.

### Parameter Description

* givenString: Text to find.
* caseSensitive: If this option is set to _true_, only strings that match the case of the whole word will be returned.
* wholeWord: If this option is set to _true_, only strings that match the whole word will be returned. The case of the words will not be matched.

The following code example illustrates the usage of the FindNext method.



{% highlight  c# %}

//Finds and replaces a particular table.

IWTable table = doc.Sections[0].Tables[0];

TextSelection selc = doc.FindNext(table as TextBodyItem, "textAA", false, false);

WTextRange range = selc.GetAsOneRange();

range.Text = "TextReplaced";



//Finds and replaces from a particular paragraph.

IWTable table1 = doc.Sections[0].Tables[0];

IWParagraph par = table1.Rows[1].Cells[0].Paragraphs[0];

TextSelection sel1 = doc.FindNext(par as TextBodyItem, "ref AA", false, false);

WTextRange range1 = sel1.GetAsOneRange();

range1.Text = "New Text";


{% endhighlight   %}
{% highlight  vbnet %}




'Finds and replaces a particular table.

Dim table As IWTable = doc.Sections(0).Tables(0)

Dim selc As TextSelection = doc.FindNext(TryCast(table, TextBodyItem), "textAA", False, False)

Dim range As WTextRange = selc.GetAsOneRange()

range.Text = "TextReplaced"



'Finds and replaces from a particular paragraph.Dim table1 As IWTable = doc.Sections(0).Tables(0)

Dim par As IWParagraph = table1.Rows(1).Cells(0).Paragraphs(0)

Dim sel1 As TextSelection = doc.FindNext(TryCast(par, TextBodyItem), "ref AA", False, False)

Dim range1 As WTextRange = sel1.GetAsOneRange()

range1.Text = "New Text"

{% endhighlight   %}

### ResetFindNext Method

This method simply resets the FindNext method. The following code example illustrates this.


{% highlight  c# %}




document.ResetFindNext();





document.ResetFindNext()

{% endhighlight   %}

### FindSingleLine and FindNextSingleLine Methods

FindSingleLine method is used to find an entry in a document with a specified text of regular expression, including the newline or carriage return. This works in the same way as the SingleLine mode of .NET Regex. Note that the Find method will find the text only in a single paragraph without any newlines or carriage return considerations.

_Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
FindSingleLine(Regex)</td><td>
Finds the first entry of specified pattern in the single-line mode. </td></tr>
<tr>
<td>
FindSingleLine(String, Boolean, Boolean)</td><td>
Finds the first entry of the given text in the single-line mode with the Boolean options case sensitiveness and whole word.</td></tr>
</table>


It is also possible to find a string with SingleLine mode from a particular region by using the FindNextSingleLine method of the WordDocument class.

_Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
FindNextSingleLine(TextBodyItem, Regex)</td><td>
Finds the next text that fit the specified pattern starting from start TextBodyItem by using single-line mode. </td></tr>
<tr>
<td>
FindNextSingleLine(TextBodyItem, String, Boolean, Boolean)</td><td>
Finds the next given text starting from specified. TextBodyItem by using single-line mode with the Boolean options case sensitiveness and whole word.</td></tr>
</table>


The following code example illustrates how to find a string in the SingleLine mode.



{% highlight  c# %}

WordDocument doc = new WordDocument("Sample.doc");

string search = "\\[start\\](.*)\\[end\\]";



//The singleline option causes \r\n to be included in .*

Regex expr = new Regex(search, RegexOptions.Singleline);



WTable table = doc.Sections[0].Tables[0] as WTable;

TextSelection[] sel = doc.FindNextSingleLine(table as TextBodyItem, expr);




{% endhighlight   %}
{% highlight  vbnet %}


Dim doc As New WordDocument("Sample.doc")

Dim search As String = "\[start\](.*)\[end\]"



'The singleline option causes \r\n to be included in .*

Dim expr As New Regex(search, RegexOptions.Singleline)



Dim tab As WTable = TryCast(doc.Sections(0).Tables(0), WTable)

Dim sel As TextSelection() = doc.FindNextSingleLine(TryCast(tab, TextBodyItem), expr)
{% endhighlight  %}

## Replace

This feature provides support to replace a particular string with another string. This is also one of the most essential features of DocIO. The following methods provide support to perform the replace operation:

* Replace
* ReplaceSingleLine

### Replace Method

Replace method provides support to replace text in the Word document. The following are the possible input parameters of the Replace method:

* Pattern: Character pattern (instance of Regex class).
* Replace: Replace string.
* Given: String to be replaced.
* CaseSensitive: If this option is set to _true_, only strings that match the case of the whole word will be returned.
* WholeWord: If this option is set to _true_, only strings that match the whole word will be returned. The case of the words will not be matched.
* SaveFormatting: If this option is set to _true_, it will preserve the existing place holder formatting.

The following are the overloads of the Replace method:

* Replace(Regex pattern, string replace): Replaces all occurrences of a character pattern specified by a regular expression with replace string.
* Replace(string given, string replace, bool caseSensitive, bool wholeWord): Replaces all entries of given string with replace string that matches the case and whole word.
* Replace(Regex pattern, TextSelection textSelection): Replaces all entries of given regular expression with the TextRangesHolder (TextSelection).
* Replace(string given, TextSelection textSelection, bool caseSensitive, bool wholeWord): Replaces all entries of the given string with TextSelection that matches the case and whole word.
* Replace(Regex pattern, TextBodyPart bodyPart): Replaces all entries of given regular expression with the TextBodyPart.
* Replace(string given, TextBodyPart bodyPart, bool caseSensitive, bool wholeWord): Replaces all entries of the given string with the TextBodyPart that matches the case and whole word.
* Replace(string given, IWordDocument replaceDoc, bool caseSensitive, bool wholeWord, bool saveFormatting): Replaces all entries of given string with the given Word document that matches the case, whole word, and formatting (to preserve the formatting of the existing place holder or the new document place holder).
* Replace(string given, TextBodyPart bodyPart, bool caseSensitive, bool wholeWord, bool saveFormatting): Replaces all entries of the given string with the given TextBodyPart that matches the case, whole word, and formatting.
* Replace(string given, TextSelection textSelection, bool caseSensitive, bool wholeWord, bool saveFormatting): Replaces all entries of given string with TextSelection that matches the case, whole word, and formatting.







Example 1:

{% highlight  c# %}

//This sample replaces the specified regular expression with a Picture.

TextBodyPart textBodyPart = new TextBodyPart( doc );

Image image = Image.FromFile( ImagesPath + "Image.gif" );

WPicture pict = new WPicture( doc );

pict.LoadImage( image );



WParagraph para = new WParagraph( doc );

para.Items.Add( pict );

textBodyPart.BodyItems.Insert( 0, para );

doc.Replace( new Regex( "A" ), textBodyPart );
{% endhighlight   %}


Example 2:

{% highlight  c# %}

WordDocument docSource1 = new WordDocument();

docSource1.Open( DocumentsPath + FINDSOURCE1 );

WordDocument docSource2 = new WordDocument();

docSource2.Open( DocumentsPath + FINDSOURCE2 );

WordDocument docTemplate = new WordDocument();

docTemplate.Open( DocumentsPath + FINDTEMPLATE );



//Finds and returns entry of specified regular expression along with formatting.

TextSelection rangesHolder1 = docSource1.Find( "The PlaceHolder1 was replaced by

this sample Text.", false, false );



//Creates new TextSelection instance, with text and its formatting specified by character range. In current sample character range is a paragraph's range of symbols from 1 to 4 position.

TextSelection rangesHolder2 = new TextSelection( docSource2.LastParagraph, 1, 4 );



docTemplate.Replace( new Regex( "PlaceHolder1" ), rangesHolder1 );

docTemplate.Replace( new Regex( "PlaceHolder2" ), rangesHolder2 );




{% endhighlight   %}


Example 1:
{% highlight  vbnet %}


'This sample replaces the specified regular expression with a Picture.

Dim textBodyPart As TextBodyPart = New TextBodyPart(doc)

Dim image As Image = image.FromFile(ImagesPath and "Image.gif")

Dim pict As WPicture = New WPicture(doc)

pict.LoadImage(image)



Dim para As WParagraph = New WParagraph(doc)

para.Items.Add(pict)

textBodyPart.BodyItems.Insert(0, para)

doc.Replace(New Regex("A"), textBodyPart) 

{% endhighlight   %}


Example 2:

{% highlight  vbnet %}

Dim docSource1 As WordDocument = New WordDocument()

docSource1.Open(DocumentsPath + FINDSOURCE1)

Dim docSource2 As WordDocument = New WordDocument()

docSource2.Open(DocumentsPath + FINDSOURCE2)

Dim docTemplate As WordDocument = New WordDocument()

docTemplate.Open(DocumentsPath + FINDTEMPLATE)



'Finds and returns entry of specified regular expression along with formatting.

Dim rangesHolder1 As TextSelection = docSource1.Find("The PlaceHolder1 was replaced by this sample Text.", False, False)



'Creates new TextSelection instance, with text and its formatting specified by character range. In the current sample character range is a paragraph's range of symbols from 1 to 4 position.

Dim rangesHolder2 As TextSelection = NewTextSelection(docSource2.LastParagraph, 1, 4)

docTemplate.Replace(New Regex("PlaceHolder1"), rangesHolder1)

docTemplate.Replace(New Regex("PlaceHolder2"), rangesHolder2)

{% endhighlight   %}

If you want to replace the first occurrence of a particular text alone, which appears more than once, you must set doc.ReplaceFirst property to _true_.



{% highlight  c# %}

doc.ReplaceFirst = true;





 doc.ReplaceFirst = true;

{% endhighlight   %}

### ReplaceSingleLine Method

It is also possible to replace a string with .NET Regex SingleLine mode by using the ReplaceSingleLine method of DocIO. You can find the specified text of regular expression including the newline or carriage return and replace it with the given text.

The following table lists the overloads of this method.

_Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
ReplaceSingleLine(Regex, TextBodyPart)</td><td>
Replaces the pattern with specified replacement in single-line mode.</td></tr>
<tr>
<td>
ReplaceSingleLine(Regex, TextSelection)</td><td>
Replaces the given pattern with a text selection in single-line mode.</td></tr>
<tr>
<td>
ReplaceSingleLine(Regex, String)</td><td>
Replaces all entries with specified pattern with replace text in single-line mode.</td></tr>
<tr>
<td>
ReplaceSingleLine(String, TextBodyPart, Boolean, Boolean)</td><td>
Replaces given text that matches the case and whole word with specified replacement in single-line mode.</td></tr>
<tr>
<td>
ReplaceSingleLine(String, TextSelection, Boolean, Boolean)</td><td>
Replaces given text that matches the case and whole word with replacement in single-line mode.</td></tr>
<tr>
<td>
ReplaceSingleLine(String, String, Boolean, Boolean)</td><td>
Replaces all entries of given text that match the case and whole word with replaced text in single-line mode.</td></tr>
</table>


The following code example illustrates the SingleLine mode replacement.



{% highlight  c# %}

 WordDocument doc = new WordDocument("sample.doc");

string search = "\\|(.|\r\n|\r|\n)*?\\|";



//The singleline option causes \r\n to be included in .*

Regex expr = new Regex(search, RegexOptions.Singleline);



doc.ReplaceSingleLine(expr, "test");


{% endhighlight   %}

{% highlight  vbnet %}


Dim doc As New WordDocument("sample.doc")

Dim search As String = "\|(.|" and VB.NETCr and VB.NETLf and "|" and VB.NETCr and "|" and VB.NETLf and ")*?\|"



'The singleline option causes \r\n to be included in .*

Dim expr As New Regex(search, RegexOptions.Singleline)



doc.ReplaceSingleLine(expr, "test")

{% endhighlight   %}

